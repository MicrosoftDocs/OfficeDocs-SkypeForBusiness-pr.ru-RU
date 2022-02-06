---
title: Таблица SessionCorrelation
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: 'Таблица SessionCorrelation — это вспомогательная таблица. Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов.'
---

# <a name="sessioncorrelation-table"></a>Таблица SessionCorrelation
 
Таблица SessionCorrelation — это вспомогательная таблица. Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов. 
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Контрольная сумма** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот сервер A/V Conferencing.  <br/> |
|**CorrelationID** <br/> |nvarchar (256)  <br/> |Уникальные  <br/> |Сопоставленные сеансы будут иметь одинаковый ID корреляции.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Только для внутреннего использования.  <br/> |
   

