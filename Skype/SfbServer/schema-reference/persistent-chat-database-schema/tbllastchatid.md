---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 18fe97268f277de11740b2181235a5088807c49f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620865"
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
