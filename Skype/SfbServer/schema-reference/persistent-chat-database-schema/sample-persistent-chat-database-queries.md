---
title: Примеры запросов к базе данных сохраняемого чата
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: В этом разделе представлены примеры запросов для базы данных сохраняемой беседы.
ms.openlocfilehash: 74cb6c1029cdeaabcd74a34898731b44c71f05a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823109"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="2e8e6-103">Примеры запросов к базе данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="2e8e6-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="2e8e6-104">В этом разделе представлены примеры запросов для базы данных сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="2e8e6-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="2e8e6-105">Используйте следующий пример, чтобы получить список наиболее активных комнат сохраняемого чата после определенной даты.</span><span class="sxs-lookup"><span data-stu-id="2e8e6-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="2e8e6-106">Используйте следующий пример, чтобы получить список наиболее активных пользователей после определенной даты.</span><span class="sxs-lookup"><span data-stu-id="2e8e6-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="2e8e6-107">Используйте следующий пример, чтобы получить список всех, кто когда-либо отправлял сообщение "Hello World".</span><span class="sxs-lookup"><span data-stu-id="2e8e6-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="2e8e6-108">Используйте следующий пример, чтобы получить список членства в группах для определенного участника.</span><span class="sxs-lookup"><span data-stu-id="2e8e6-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="2e8e6-109">Используйте следующий пример, чтобы получить список всех комнат чата, в которые непосредственно входит пользователь Джейн Доу.</span><span class="sxs-lookup"><span data-stu-id="2e8e6-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="2e8e6-110">Используйте следующий пример, чтобы получить список приглашений, полученных пользователем.</span><span class="sxs-lookup"><span data-stu-id="2e8e6-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
