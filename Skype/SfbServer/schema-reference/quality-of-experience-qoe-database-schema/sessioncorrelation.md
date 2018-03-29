---
title: Таблица SessionCorrelation
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Таблица sessioncorrelation представляет собой вспомогательную таблицу. Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов.
ms.openlocfilehash: 8a9c9661b10548bf3ebf402aa4654fced2ca709b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="sessioncorrelation-table"></a>Таблица SessionCorrelation
 
Таблица sessioncorrelation представляет собой вспомогательную таблицу. Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов. 
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Контрольная сумма** <br/> |целое  <br/> |||
|**CorrelationKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот / видеоконференций.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Уникальный  <br/> |Сопоставленным сеансам будет иметь тот же идентификатор корреляции.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Только для внутреннего использования.  <br/> |
   

