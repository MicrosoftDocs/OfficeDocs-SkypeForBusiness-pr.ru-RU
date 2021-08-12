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
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: Таблица tblLastChatId содержит последние идентификаторы чатов, которые были созданы (и использованы в таблице tblChat) для каждого пользователя.
ms.openlocfilehash: ecd707a8e6c9dbec220f137c69042c22ac6e1d8a4e46a46e4c2d8a6f035c8a0d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322941"
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
