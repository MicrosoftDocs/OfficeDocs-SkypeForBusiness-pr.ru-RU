---
title: Таблица PayloadDescription
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: Таблица PayloadDescription представляет собой вспомогательную таблицу. Каждая запись представляет один кодек, который используется в сеансе аудио или видео.
ms.openlocfilehash: 320542593479e3051992e8079abfdf9f54b0efc0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874202"
---
# <a name="payloaddescription-table"></a>Таблица PayloadDescription
 
Таблица PayloadDescription представляет собой вспомогательную таблицу. Каждая запись представляет один кодек, который используется в сеансе аудио или видео.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, обозначающий кодек.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Уникальный  <br/> |Имя кодека.  <br/> |
   

