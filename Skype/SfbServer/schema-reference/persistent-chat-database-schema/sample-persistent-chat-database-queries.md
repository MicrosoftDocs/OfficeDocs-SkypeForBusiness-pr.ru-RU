---
title: Примеры запросов к базе данных сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: В этом разделе содержатся примеры запросов для базы данных сохраняемого чата.
ms.openlocfilehash: fef40c2f36547fb0772d2e938bf8259246ec2055
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295610"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="acd48-103">Примеры запросов к базе данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="acd48-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="acd48-104">В этом разделе содержатся примеры запросов для базы данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="acd48-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="acd48-105">Чтобы получить список наиболее активных сохраненных комнат чата после определенной даты, используйте следующий пример.</span><span class="sxs-lookup"><span data-stu-id="acd48-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="acd48-106">Чтобы получить список наиболее активных пользователей после определенной даты, используйте следующий пример.</span><span class="sxs-lookup"><span data-stu-id="acd48-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="acd48-107">В следующем примере показано, как получить список всех тех, кто когда-либо отправил сообщение с помощью "Hello World".</span><span class="sxs-lookup"><span data-stu-id="acd48-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="acd48-108">С помощью приведенного ниже примера можно получить список участников группы для определенного участника.</span><span class="sxs-lookup"><span data-stu-id="acd48-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="acd48-109">В следующем примере показано, как получить список всех комнат чата, в которых входит пользователь, Джейн Seleznyov.</span><span class="sxs-lookup"><span data-stu-id="acd48-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="acd48-110">С помощью приведенного ниже примера можно получить список приглашенных, полученных пользователем.</span><span class="sxs-lookup"><span data-stu-id="acd48-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
