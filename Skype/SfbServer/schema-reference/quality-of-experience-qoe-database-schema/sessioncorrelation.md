---
title: Таблица SessionCorrelation
ms.reviewer: ''
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
ms.openlocfilehash: 8c41ab5c52c6b4d06a3c3953e8d969488680e8d3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212118"
---
# <a name="sessioncorrelation-table"></a>Таблица SessionCorrelation
 
Таблица sessioncorrelation представляет собой вспомогательную таблицу. Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Контрольная сумма** <br/> |целое  <br/> |||
|**CorrelationKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот / видеоконференций.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Уникальный  <br/> |Сопоставленным сеансам будет иметь тот же идентификатор корреляции.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Только для внутреннего использования.  <br/> |
   

