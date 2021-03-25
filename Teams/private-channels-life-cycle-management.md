---
title: Управление частными каналами в Microsoft Teams с помощью API Graph
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
description: Узнайте, как управлять частными каналами в организации с помощью Graph API.
ms.openlocfilehash: e97d808bd9f544ef611b0b5e4b0456d302b4013d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117747"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="8ccbf-103">Управление жизненным циклом закрытых каналов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ccbf-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="8ccbf-104">Здесь вы найдете руководство, необходимое для управления использованием Graph API для управления частными каналами [Teams](./private-channels.md) в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-104">Here you'll find the guidance you need to manage use the Graph API to manage [Teams private channels](./private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="8ccbf-105">Укажите, могут ли участники команды создавать закрытые каналы</span><span class="sxs-lookup"><span data-stu-id="8ccbf-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="8ccbf-106">Администратор может управлять возможностью создания закрытых каналов для членов конкретных команд с помощью API Graph.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-106">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="8ccbf-107">Приведем пример.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-107">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="8ccbf-108">Создайте закрытый канал от имени владельца команды</span><span class="sxs-lookup"><span data-stu-id="8ccbf-108">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="8ccbf-109">Как администратор вы можете использовать API Graph для создания частного канала от имени владельца группы.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-109">As an admin, you can use the Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="8ccbf-110">Например, это можно сделать в случае централизации создания закрытых каналов в организации.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-110">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="8ccbf-111">Получите список всех сообщений закрытого канала</span><span class="sxs-lookup"><span data-stu-id="8ccbf-111">Get a list of all private channel messages</span></span>

<span data-ttu-id="8ccbf-112">В целях архивирования и аудита вам может понадобиться список всех сообщений и ответов, опубликованных в закрытом канале.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-112">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="8ccbf-113">Ниже описывается, как получить список с помощью API Graph.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-113">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="8ccbf-114">Найдите URL-адреса SharePoint для всех закрытых каналов в команде</span><span class="sxs-lookup"><span data-stu-id="8ccbf-114">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="8ccbf-115">Требуется ли выполнить обнаружение электронных данных или удержание по юридическим причинам для файлов в закрытом канале либо создать пользовательское приложение, которое помещает файлы в определенные закрытые каналы, вам понадобится запросить уникальные семейства веб-сайтов SharePoint, которые создаются для каждого закрытого канала.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-115">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="8ccbf-116">Как администратор вы можете использовать команды API Graph для запроса этих URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-116">As an admin, you can use Graph APIs commands to query these URLs.</span></span>

<span data-ttu-id="8ccbf-117">Эти команды можно выполнить, используя [песочницу Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="8ccbf-117">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="8ccbf-118">Чтобы получить список ИД закрытых каналов для определенной команды, используйте следующие команды, где <group_id> — ИД группы.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-118">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="8ccbf-119">Вам потребуется эта информация для последующих вызовов.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-119">You'll need this in subsequent calls.</span></span> <span data-ttu-id="8ccbf-120">(Вы легко найдете ИД группы в ссылке на команду.)</span><span class="sxs-lookup"><span data-stu-id="8ccbf-120">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="8ccbf-121">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-121">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="8ccbf-122">**Ответ**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-122">**Response**</span></span>

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

2. <span data-ttu-id="8ccbf-123">Для каждого закрытого канала, для которого нужно получить URL-адрес SharePoint, выполните следующий запрос, где &lt;channel_id&gt; — ИД канала.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-123">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="8ccbf-124">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-124">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="8ccbf-125">**Ответ**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-125">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="8ccbf-126">Составьте список и обновите роли владельцев и участников в закрытом канале</span><span class="sxs-lookup"><span data-stu-id="8ccbf-126">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="8ccbf-127">Возможно, вы хотите составить список владельцев и участников закрытого канала, чтобы решить, нужно ли повысить уровень некоторых участников до владельца.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-127">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="8ccbf-128">Это происходит в тех случаях, когда владельцы закрытых каналов покинули организацию и необходима помощь администратора, чтобы заявить о праве собственности на закрытый канал.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-128">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="8ccbf-129">Как администратор вы можете использовать API Graph для выполнения этих действий.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-129">As an admin, you can use the Graph API to perform these actions.</span></span>

<span data-ttu-id="8ccbf-130">Эти команды можно выполнить, используя [песочницу Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="8ccbf-130">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="8ccbf-131">Используйте следующие команды, где &lt;group_id&gt; — ИД группы, а &lt;channel_id&gt; — ИД канала.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-131">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="8ccbf-132">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-132">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="8ccbf-133">**Ответ**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-133">**Response**</span></span>

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
2. <span data-ttu-id="8ccbf-134">Чтобы повысить уровень участника до владельца, используйте следующие команды, где &lt;group_id&gt;, &lt;channel_id&gt; и &lt;id&gt; возвращаются из предыдущего вызова.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-134">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="8ccbf-135">Обратите внимание, что &lt;id&gt; и &lt;userId&gt;, возвращенные из предыдущего вызова, не совпадают и не являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-135">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="8ccbf-136">Убедитесь, что вы используете &lt;id&gt;.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-136">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="8ccbf-137">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-137">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="8ccbf-138">**Ответ**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-138">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="8ccbf-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8ccbf-139">Related topics</span></span>

[<span data-ttu-id="8ccbf-140">Использование Microsoft Graph API для работы с Teams</span><span class="sxs-lookup"><span data-stu-id="8ccbf-140">Use the Microsoft Graph API to work with Teams</span></span>](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[<span data-ttu-id="8ccbf-141">Перечисление каналов</span><span class="sxs-lookup"><span data-stu-id="8ccbf-141">List channels</span></span>](/graph/api/channel-list)

[<span data-ttu-id="8ccbf-142">Создание канала</span><span class="sxs-lookup"><span data-stu-id="8ccbf-142">Create channel</span></span>](/graph/api/channel-post)

[<span data-ttu-id="8ccbf-143">Добавление участника в канал</span><span class="sxs-lookup"><span data-stu-id="8ccbf-143">Add member to channel</span></span>](/graph/api/conversationmember-add)

[<span data-ttu-id="8ccbf-144">Обновление участника в канале</span><span class="sxs-lookup"><span data-stu-id="8ccbf-144">Update member in channel</span></span>](/graph/api/conversationmember-update)

[<span data-ttu-id="8ccbf-145">Удаление участника из канала</span><span class="sxs-lookup"><span data-stu-id="8ccbf-145">Remove member from channel</span></span>](/graph/api/conversationmember-delete)