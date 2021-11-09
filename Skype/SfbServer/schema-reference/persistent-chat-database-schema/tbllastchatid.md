---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: Таблица tblLastChatId содержит последние идентификаторы чатов, которые были созданы (и использованы в таблице tblChat) для каждого пользователя.
ms.openlocfilehash: a69c8ee112d507359a5582464ce39b7cbae89f4c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838441"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
Таблица tblLastChatId содержит последние идентификаторы чатов, которые были созданы (и использованы в таблице tblChat) для каждого пользователя.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, not null  <br/> |Идентификатор узла (только типа комнаты чата).  <br/> |
|lastChatID  <br/> |bigint, not null  <br/> |Идентификатор последнего чата.  <br/> |
   
**Keys**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Первичный ключ (для обработки достаточно nodeID).  <br/> |
|nodeID  <br/> |Внешний ключ с поиском в таблице tblNode.nodeID.  <br/> |
   
## <a name="see-also"></a>См. также

[tblChat](tblchat.md)
