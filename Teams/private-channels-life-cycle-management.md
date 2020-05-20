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
ms.openlocfilehash: 154cde6ad8371b2d9f902bf3803f48e72ade0a77
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321707"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="0aafc-103">Управление жизненным циклом частных каналов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0aafc-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="0aafc-104">Здесь вы найдете рекомендации, которые необходимо выполнить для управления жизненным циклом [личных каналов](private-channels.md) в Организации.</span><span class="sxs-lookup"><span data-stu-id="0aafc-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0aafc-105">Если вы используете шаги PowerShell, описанные в этой статье, чтобы управлять личными каналами, необходимо установить и использовать самую последнюю версию модуля Teams PowerShell из [коллекции тестов PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="0aafc-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="0aafc-106">Инструкции по установке модуля приведены в [статье Установка предварительной версии модуля PowerShell Teams](install-prerelease-teams-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="0aafc-106">For steps on how to install the module, see [Install the pre-release version of the Teams PowerShell module](install-prerelease-teams-powershell-module.md).</span></span> <span data-ttu-id="0aafc-107">Самая свежая доступная версия модуля PowerShell Teams не поддерживает управление личными каналами.</span><span class="sxs-lookup"><span data-stu-id="0aafc-107">The latest publicly available version of the Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="0aafc-108">Определение возможности создания личных каналов участниками группы</span><span class="sxs-lookup"><span data-stu-id="0aafc-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="0aafc-109">Владельцы групп могут включать и отключать возможность создания личных каналов для пользователей в параметрах группы.</span><span class="sxs-lookup"><span data-stu-id="0aafc-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="0aafc-110">Для этого на вкладке Параметры для команды отключите или включите **параметр** **Разрешить участникам создавать закрытые каналы**.</span><span class="sxs-lookup"><span data-stu-id="0aafc-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="0aafc-111">Администраторы могут использовать Graph API для управления тем, могут ли участники создавать закрытые каналы в конкретных командах.</span><span class="sxs-lookup"><span data-stu-id="0aafc-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="0aafc-112">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="0aafc-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="0aafc-113">Настройка возможности создания частных каналов для пользователей в Организации</span><span class="sxs-lookup"><span data-stu-id="0aafc-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="0aafc-114">Администраторы могут настроить политики с помощью центра администрирования Microsoft Teams или PowerShell, чтобы управлять тем, какие пользователи в организации могут создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="0aafc-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0aafc-115">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0aafc-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="0aafc-116">Используйте политики Teams, чтобы настроить, какие пользователи в организации смогут создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="0aafc-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="0aafc-117">Дополнительные сведения можно найти в разделе [Управление политиками Teams в Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0aafc-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0aafc-118">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="0aafc-118">Using PowerShell</span></span>

<span data-ttu-id="0aafc-119">С помощью **CsTeamsChannelsPolicy** можно указать, какие пользователи в вашей организации могут создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="0aafc-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="0aafc-120">Установите для параметра **AllowPrivateChannelCreation** значение **true** , чтобы пользователи, которым назначена политика, могли создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="0aafc-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="0aafc-121">Если задать для параметра **значение false** , возможность создания частных каналов для пользователей, которым назначена политика, будет отключена.</span><span class="sxs-lookup"><span data-stu-id="0aafc-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="0aafc-122">Дополнительные сведения можно найти в статье [Создание и CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0aafc-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="0aafc-123">Создание закрытого канала от имени владельца команды</span><span class="sxs-lookup"><span data-stu-id="0aafc-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="0aafc-124">Администратор может использовать PowerShell или Graph API для создания закрытого канала от имени владельца команды.</span><span class="sxs-lookup"><span data-stu-id="0aafc-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="0aafc-125">Например, это может потребоваться, если ваша организация хотела бы централизовать создание частных каналов.</span><span class="sxs-lookup"><span data-stu-id="0aafc-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0aafc-126">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="0aafc-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="0aafc-127">Использование Graph API</span><span class="sxs-lookup"><span data-stu-id="0aafc-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="0aafc-128">Получение списка всех сообщений личного канала</span><span class="sxs-lookup"><span data-stu-id="0aafc-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="0aafc-129">Для архивации и аудита может потребоваться просмотреть список всех сообщений и ответов, опубликованных в частном канале.</span><span class="sxs-lookup"><span data-stu-id="0aafc-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="0aafc-130">Ниже показано, как использовать Graph API.</span><span class="sxs-lookup"><span data-stu-id="0aafc-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="0aafc-131">Поиск URL-адресов SharePoint для всех частных каналов в команде</span><span class="sxs-lookup"><span data-stu-id="0aafc-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="0aafc-132">Если вы собираетесь проводить обнаружение электронных данных или судебных удержаний по файлам в частном канале или собираетесь создавать пользовательские приложения, которые размещают файлы в определенных частных каналах, вам будет предложено запросить уникальные семейства веб-сайтов SharePoint, созданные для каждого закрытого канала.</span><span class="sxs-lookup"><span data-stu-id="0aafc-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="0aafc-133">Администратор может использовать команды PowerShell или Graph API для запроса этих URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="0aafc-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0aafc-134">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="0aafc-134">Using PowerShell</span></span>

1. <span data-ttu-id="0aafc-135">Установите [консоль управления SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) и подключитесь к ней с помощью учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="0aafc-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="0aafc-136">Запустите следующую команду, где &lt; group_id &gt; — идентификатор группы.</span><span class="sxs-lookup"><span data-stu-id="0aafc-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="0aafc-137">(Идентификатор группы можно легко найти в ссылке на команду.)</span><span class="sxs-lookup"><span data-stu-id="0aafc-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="0aafc-138">Использование Graph API</span><span class="sxs-lookup"><span data-stu-id="0aafc-138">Using Graph API</span></span>

<span data-ttu-id="0aafc-139">Эти команды можно выполнить с помощью [проводника диаграмм](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="0aafc-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="0aafc-140">Воспользуйтесь приведенными ниже сведениями, чтобы получить список идентификаторов частных каналов для конкретной команды, где <group_id> является ИДЕНТИФИКАТОРом группы для группы.</span><span class="sxs-lookup"><span data-stu-id="0aafc-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="0aafc-141">Это потребуется при последующих звонках.</span><span class="sxs-lookup"><span data-stu-id="0aafc-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="0aafc-142">(Идентификатор группы можно легко найти в ссылке на команду).</span><span class="sxs-lookup"><span data-stu-id="0aafc-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="0aafc-143">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="0aafc-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="0aafc-144">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="0aafc-144">**Response**</span></span>

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

2. <span data-ttu-id="0aafc-145">Для каждого закрытого канала, для которого требуется получить URL-адрес SharePoint, сделайте следующий запрос, где &lt; channel_id &gt; — идентификатор канала.</span><span class="sxs-lookup"><span data-stu-id="0aafc-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="0aafc-146">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="0aafc-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="0aafc-147">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="0aafc-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="0aafc-148">Перечисление и обновление ролей владельцев и участников в частном канале</span><span class="sxs-lookup"><span data-stu-id="0aafc-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="0aafc-149">Вам может потребоваться указать владельцев и участников закрытого канала, чтобы решить, нужно ли распространить определенных участников закрытого канала на владельца.</span><span class="sxs-lookup"><span data-stu-id="0aafc-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="0aafc-150">Это может быть вызвано тем, что у вас есть владельцы частных каналов, которые оставили организацию и для личного канала требуется помощь администратора для утверждения прав собственности на канал.</span><span class="sxs-lookup"><span data-stu-id="0aafc-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="0aafc-151">Администратор может использовать команды PowerShell или Graph API для запроса этих URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="0aafc-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0aafc-152">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="0aafc-152">Using PowerShell</span></span>

1. <span data-ttu-id="0aafc-153">Запустите следующую команду, где &lt; group_id &gt; — идентификатор группы, а &lt; channel_name &gt; — имя канала.</span><span class="sxs-lookup"><span data-stu-id="0aafc-153">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="0aafc-154">Повышение роли участника до владельца.</span><span class="sxs-lookup"><span data-stu-id="0aafc-154">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="0aafc-155">Использование Graph API</span><span class="sxs-lookup"><span data-stu-id="0aafc-155">Using Graph API</span></span>

<span data-ttu-id="0aafc-156">Эти команды можно выполнить с помощью [проводника диаграмм](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="0aafc-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="0aafc-157">Используйте следующую команду, где &lt; group_id &gt; — идентификатор группы, а &lt; channel_id &gt; — идентификатор канала.</span><span class="sxs-lookup"><span data-stu-id="0aafc-157">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="0aafc-158">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="0aafc-158">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="0aafc-159">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="0aafc-159">**Response**</span></span>

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
2. <span data-ttu-id="0aafc-160">Используйте указанные ниже действия, чтобы повысить роль участника до владельца, где в &lt; &gt; &lt; &gt; &lt; &gt; предыдущем вызове возвращаются group_id, channel_id и идентификатор.</span><span class="sxs-lookup"><span data-stu-id="0aafc-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="0aafc-161">Обратите внимание, что &lt; идентификатор &gt; и &lt; UserID, &gt; возвращенные из предыдущего звонка, не являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="0aafc-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="0aafc-162">Убедитесь, что вы используете &lt; ID &gt; .</span><span class="sxs-lookup"><span data-stu-id="0aafc-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="0aafc-163">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="0aafc-163">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="0aafc-164">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="0aafc-164">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="0aafc-165">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0aafc-165">Related topics</span></span>

- [<span data-ttu-id="0aafc-166">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="0aafc-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="0aafc-167">Использование Microsoft Graph API для работы с Teams</span><span class="sxs-lookup"><span data-stu-id="0aafc-167">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="0aafc-168">Каналы списка</span><span class="sxs-lookup"><span data-stu-id="0aafc-168">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="0aafc-169">Создать канал</span><span class="sxs-lookup"><span data-stu-id="0aafc-169">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="0aafc-170">Добавить участника в канал</span><span class="sxs-lookup"><span data-stu-id="0aafc-170">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="0aafc-171">Обновить пользователя в канале</span><span class="sxs-lookup"><span data-stu-id="0aafc-171">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="0aafc-172">Удалить участника из канала</span><span class="sxs-lookup"><span data-stu-id="0aafc-172">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
