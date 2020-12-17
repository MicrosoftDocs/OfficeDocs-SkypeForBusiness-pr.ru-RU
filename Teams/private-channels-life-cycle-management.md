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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="6f362-103">Управление жизненным циклом закрытых каналов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f362-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="6f362-104">В этой статье приводятся необходимые инструкции по управлению жизненным циклом [закрытых каналов](private-channels.md) в организации.</span><span class="sxs-lookup"><span data-stu-id="6f362-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f362-105">Чтобы использовать PowerShell для управления закрытыми каналами, как описано в этой статье, нужно установить и использовать модуль общедоступной предварительной версии PowerShell для Teams из [коллекции PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="6f362-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="6f362-106">Инструкции по установке модуля см. в статье [Установка PowerShell для Teams](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="6f362-106">For steps on how to install the module, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span> <span data-ttu-id="6f362-107">Модуль последней общедоступной версии PowerShell для Teams не поддерживает управление закрытыми каналами.</span><span class="sxs-lookup"><span data-stu-id="6f362-107">The latest General Availability Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="6f362-108">Укажите, могут ли участники команды создавать закрытые каналы</span><span class="sxs-lookup"><span data-stu-id="6f362-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="6f362-109">Владельцы команды могут включить или отключить возможность создания закрытых каналов для участников в параметрах команды.</span><span class="sxs-lookup"><span data-stu-id="6f362-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="6f362-110">Для этого на вкладке **Параметры** команды включите или отключите параметр **Разрешить участникам создавать закрытые каналы**.</span><span class="sxs-lookup"><span data-stu-id="6f362-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="6f362-111">Администратор может управлять возможностью создания закрытых каналов для членов конкретных команд с помощью API Graph.</span><span class="sxs-lookup"><span data-stu-id="6f362-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="6f362-112">Приведем пример.</span><span class="sxs-lookup"><span data-stu-id="6f362-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="6f362-113">Укажите, могут ли пользователи в вашей организации создавать закрытые каналы</span><span class="sxs-lookup"><span data-stu-id="6f362-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="6f362-114">Администратор может задать политики с помощью Центра администрирования Microsoft Teams или PowerShell, чтобы выбрать пользователей в организации, которым разрешено создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="6f362-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6f362-115">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f362-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6f362-116">Используйте политики команд, чтобы указать пользователей в организации, которым разрешено создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="6f362-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="6f362-117">Дополнительные сведения см. в статье [Управление политиками команд в Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6f362-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6f362-118">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f362-118">Using PowerShell</span></span>

<span data-ttu-id="6f362-119">Используйте **CsTeamsChannelsPolicy**, чтобы указать пользователей в организации, которым разрешено создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="6f362-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="6f362-120">Задайте значение **true** для параметра **AllowPrivateChannelCreation**, чтобы разрешить пользователям, которым назначена политика, создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="6f362-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="6f362-121">Если для этого параметра задать значение **false**, возможность создания закрытых каналов будет отключена для пользователей, которым назначена политика.</span><span class="sxs-lookup"><span data-stu-id="6f362-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="6f362-122">Дополнительные сведения см. в статье [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6f362-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="6f362-123">Создайте закрытый канал от имени владельца команды</span><span class="sxs-lookup"><span data-stu-id="6f362-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="6f362-124">Администратор может создать закрытый канал от имени владельца команды с помощью PowerShell или API Graph.</span><span class="sxs-lookup"><span data-stu-id="6f362-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="6f362-125">Например, это можно сделать в случае централизации создания закрытых каналов в организации.</span><span class="sxs-lookup"><span data-stu-id="6f362-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6f362-126">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f362-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="6f362-127">С помощью API Graph</span><span class="sxs-lookup"><span data-stu-id="6f362-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="6f362-128">Получите список всех сообщений закрытого канала</span><span class="sxs-lookup"><span data-stu-id="6f362-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="6f362-129">В целях архивирования и аудита вам может понадобиться список всех сообщений и ответов, опубликованных в закрытом канале.</span><span class="sxs-lookup"><span data-stu-id="6f362-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="6f362-130">Ниже описывается, как получить список с помощью API Graph.</span><span class="sxs-lookup"><span data-stu-id="6f362-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="6f362-131">Найдите URL-адреса SharePoint для всех закрытых каналов в команде</span><span class="sxs-lookup"><span data-stu-id="6f362-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="6f362-132">Требуется ли выполнить обнаружение электронных данных или удержание по юридическим причинам для файлов в закрытом канале либо создать пользовательское приложение, которое помещает файлы в определенные закрытые каналы, вам понадобится запросить уникальные семейства веб-сайтов SharePoint, которые создаются для каждого закрытого канала.</span><span class="sxs-lookup"><span data-stu-id="6f362-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="6f362-133">Администратор может запросить эти URL-адреса с помощью команд PowerShell или API Graph.</span><span class="sxs-lookup"><span data-stu-id="6f362-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6f362-134">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f362-134">Using PowerShell</span></span>

1. <span data-ttu-id="6f362-135">Установите [командную консоль SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) и подключитесь к ней с учетной записью администратора.</span><span class="sxs-lookup"><span data-stu-id="6f362-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="6f362-136">Выполните следующие команды, где &lt;group_id&gt; — ИД группы.</span><span class="sxs-lookup"><span data-stu-id="6f362-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="6f362-137">(Вы легко найдете ИД группы в ссылке на команду.)</span><span class="sxs-lookup"><span data-stu-id="6f362-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="6f362-138">С помощью API Graph</span><span class="sxs-lookup"><span data-stu-id="6f362-138">Using Graph API</span></span>

<span data-ttu-id="6f362-139">Эти команды можно выполнить, используя [песочницу Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="6f362-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="6f362-140">Чтобы получить список ИД закрытых каналов для определенной команды, используйте следующие команды, где <group_id> — ИД группы.</span><span class="sxs-lookup"><span data-stu-id="6f362-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="6f362-141">Вам потребуется эта информация для последующих вызовов.</span><span class="sxs-lookup"><span data-stu-id="6f362-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="6f362-142">(Вы легко найдете ИД группы в ссылке на команду.)</span><span class="sxs-lookup"><span data-stu-id="6f362-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="6f362-143">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="6f362-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="6f362-144">**Ответ**</span><span class="sxs-lookup"><span data-stu-id="6f362-144">**Response**</span></span>

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

2. <span data-ttu-id="6f362-145">Для каждого закрытого канала, для которого нужно получить URL-адрес SharePoint, выполните следующий запрос, где &lt;channel_id&gt; — ИД канала.</span><span class="sxs-lookup"><span data-stu-id="6f362-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="6f362-146">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="6f362-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="6f362-147">**Ответ**</span><span class="sxs-lookup"><span data-stu-id="6f362-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="6f362-148">Составьте список и обновите роли владельцев и участников в закрытом канале</span><span class="sxs-lookup"><span data-stu-id="6f362-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="6f362-149">Возможно, вы хотите составить список владельцев и участников закрытого канала, чтобы решить, нужно ли повысить уровень некоторых участников до владельца.</span><span class="sxs-lookup"><span data-stu-id="6f362-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="6f362-150">Это происходит в тех случаях, когда владельцы закрытых каналов покинули организацию и необходима помощь администратора, чтобы заявить о праве собственности на закрытый канал.</span><span class="sxs-lookup"><span data-stu-id="6f362-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="6f362-151">Администратор может выполнить эти действия с помощью Центра администрирования Microsoft Teams, PowerShell или API Graph.</span><span class="sxs-lookup"><span data-stu-id="6f362-151">As an admin, you can use the Microsoft Teams admin center, PowerShell, or Graph API to perform these actions.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6f362-152">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f362-152">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6f362-153">Сведения об управлении участниками команды с помощью Центра администрирования Microsoft Teams см. в статье [Управление командами в Центре администрирования Microsoft Teams](manage-teams-in-modern-portal.md).</span><span class="sxs-lookup"><span data-stu-id="6f362-153">To learn how to manage team members using the Microsoft Teams admin center, see [Manage teams in the Microsoft Teams admin center](manage-teams-in-modern-portal.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6f362-154">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f362-154">Using PowerShell</span></span>

1. <span data-ttu-id="6f362-155">Выполните следующие команды, где &lt;group_id&gt; — ИД группы, а &lt;channel_name&gt; — имя канала.</span><span class="sxs-lookup"><span data-stu-id="6f362-155">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="6f362-156">Повысьте уровень участника до владельца.</span><span class="sxs-lookup"><span data-stu-id="6f362-156">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="6f362-157">С помощью API Graph</span><span class="sxs-lookup"><span data-stu-id="6f362-157">Using Graph API</span></span>

<span data-ttu-id="6f362-158">Эти команды можно выполнить, используя [песочницу Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="6f362-158">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="6f362-159">Используйте следующие команды, где &lt;group_id&gt; — ИД группы, а &lt;channel_id&gt; — ИД канала.</span><span class="sxs-lookup"><span data-stu-id="6f362-159">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="6f362-160">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="6f362-160">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="6f362-161">**Ответ**</span><span class="sxs-lookup"><span data-stu-id="6f362-161">**Response**</span></span>

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
2. <span data-ttu-id="6f362-162">Чтобы повысить уровень участника до владельца, используйте следующие команды, где &lt;group_id&gt;, &lt;channel_id&gt; и &lt;id&gt; возвращаются из предыдущего вызова.</span><span class="sxs-lookup"><span data-stu-id="6f362-162">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="6f362-163">Обратите внимание, что &lt;id&gt; и &lt;userId&gt;, возвращенные из предыдущего вызова, не совпадают и не являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="6f362-163">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="6f362-164">Убедитесь, что вы используете &lt;id&gt;.</span><span class="sxs-lookup"><span data-stu-id="6f362-164">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="6f362-165">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="6f362-165">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="6f362-166">**Ответ**</span><span class="sxs-lookup"><span data-stu-id="6f362-166">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="6f362-167">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6f362-167">Related topics</span></span>

- [<span data-ttu-id="6f362-168">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="6f362-168">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="6f362-169">Использование Microsoft Graph API для работы с Teams</span><span class="sxs-lookup"><span data-stu-id="6f362-169">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="6f362-170">Перечисление каналов</span><span class="sxs-lookup"><span data-stu-id="6f362-170">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="6f362-171">Создание канала</span><span class="sxs-lookup"><span data-stu-id="6f362-171">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="6f362-172">Добавление участника в канал</span><span class="sxs-lookup"><span data-stu-id="6f362-172">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="6f362-173">Обновление участника в канале</span><span class="sxs-lookup"><span data-stu-id="6f362-173">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="6f362-174">Удаление участника из канала</span><span class="sxs-lookup"><span data-stu-id="6f362-174">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
