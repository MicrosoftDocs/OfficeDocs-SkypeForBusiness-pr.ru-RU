---
title: tblLastChatId
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
ms.openlocfilehash: dc25eb68ee1b4069ba54133548f743ca45b73e16
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505092"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
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

[tblChat](tblchat.md)