---
title: Таблица SessionCorrelation
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Таблица SessionCorrelation — это вспомогательная таблица. Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов.
ms.openlocfilehash: 2029d78a0a083bcf8817b3a819cd28e74824995d79575036ecafd85998bd5218
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314425"
---
# <a name="sessioncorrelation-table"></a>Таблица SessionCorrelation
 
Таблица SessionCorrelation — это вспомогательная таблица. Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов. 
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Контрольная сумма** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот сервер A/V Conferencing.  <br/> |
|**CorrelationID** <br/> |nvarchar (256)  <br/> |Уникальные  <br/> |Сопоставленные сеансы будут иметь одинаковый ID корреляции.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Только для внутреннего использования.  <br/> |
   

