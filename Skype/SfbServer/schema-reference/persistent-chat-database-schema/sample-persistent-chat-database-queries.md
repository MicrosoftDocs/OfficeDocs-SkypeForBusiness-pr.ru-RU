---
title: Примеры запросов к базе данных сохраняемого чата
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: В этом разделе содержатся примерные запросы для базы данных сохраняемой системы чата.
ms.openlocfilehash: 9ae2f99817cae9eb892bf7c43d68900495878abf
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756442"
---
# <a name="sample-persistent-chat-database-queries"></a>Примеры запросов к базе данных сохраняемого чата
 
В этом разделе содержатся примерные запросы для базы данных сохраняемой системы чата.
  
Используйте следующий пример, чтобы получить список наиболее активных постоянных чатов после определенной даты.
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

Используйте следующий пример, чтобы получить список наиболее активных пользователей после определенной даты.
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

Используйте следующий пример, чтобы получить список всех, кто когда-либо отправлял сообщение "Hello World".
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

Используйте следующий пример, чтобы получить список членства в группах для определенного участника.
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

Используйте следующий пример, чтобы получить список всех комнат чата, в которые непосредственно входит пользователь Джейн Доу.
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

Используйте следующий пример, чтобы получить список приглашений, полученных пользователем.
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
