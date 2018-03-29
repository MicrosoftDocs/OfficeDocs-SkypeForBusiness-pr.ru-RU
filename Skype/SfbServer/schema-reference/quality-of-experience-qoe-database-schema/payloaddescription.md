---
title: Таблица PayloadDescription
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
ms.openlocfilehash: fb4acb8182db920e25305b2be72cbc19700792bb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="payloaddescription-table"></a>Таблица PayloadDescription
 
Таблица PayloadDescription представляет собой вспомогательную таблицу. Каждая запись представляет один кодек, который используется в сеансе аудио или видео.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, обозначающий кодек.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Уникальный  <br/> |Имя кодека.  <br/> |
   

