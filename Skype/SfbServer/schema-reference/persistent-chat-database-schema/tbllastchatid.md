---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: Тблластчатид включает последний идентификатор чата, который был создан (и использован в таблице Тблчат) для каждого пользователя.
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295400"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
Тблластчатид включает последний идентификатор чата, который был создан (и использован в таблице Тблчат) для каждого пользователя.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Нодеид  <br/> |int, NOT NULL  <br/> |Идентификатор узла (комната чата — только тип).  <br/> |
|Ластчатид  <br/> |bigint, NOT NULL  <br/> |НОМЕР последнего использованного чата.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Нодеид, Ластчатид\>  <br/> |Первичный ключ (для обработки достаточно просто Нодеид).  <br/> |
|Нодеид  <br/> |Внешний ключ с подстановкой в таблице Тблноде. Нодеид.  <br/> |
   
## <a name="see-also"></a>См. также

[tblChat](tblchat.md)
