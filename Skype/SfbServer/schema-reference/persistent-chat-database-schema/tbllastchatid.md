---
title: Таблица tblLastChatId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: Таблица tblLastChatId содержит последние Идентификаторы чатов, созданного (и используемый в таблице tblChat) для каждого пользователя.
ms.openlocfilehash: 4a22dc9ba1c2dbe15ae0a24de6e4f347a62deaee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastchatid"></a>Таблица tblLastChatId
 
Таблица tblLastChatId содержит последние Идентификаторы чатов, созданного (и используемый в таблице tblChat) для каждого пользователя.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, не null  <br/> |КОД узла (только типа комнаты чата).  <br/> |
|lastChatID  <br/> |bigint, не может быть null  <br/> |Последний идентификатор чата.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<nodeID lastChatID\>  <br/> |Первичный ключ (достаточно NodeId для обработки).  <br/> |
|nodeID  <br/> |Внешний ключ с подстановкой в таблице tblNode.nodeID.  <br/> |
   
## <a name="see-also"></a>См. также

#### 

[tblChat](tblchat.md)

