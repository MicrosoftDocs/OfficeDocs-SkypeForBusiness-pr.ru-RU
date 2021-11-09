---
title: Таблица SessionCorrelation
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Таблица SessionCorrelation — это вспомогательная таблица. Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов.
ms.openlocfilehash: 706bd5c47d1a709712c7178562e535612f61332c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834907"
---
# <a name="sessioncorrelation-table"></a>Таблица SessionCorrelation
 
Таблица SessionCorrelation — это вспомогательная таблица. Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов. 
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Контрольная сумма** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот сервер A/V Conferencing.  <br/> |
|**CorrelationID** <br/> |nvarchar (256)  <br/> |Уникальные  <br/> |Сопоставленные сеансы будут иметь одинаковый ID корреляции.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Только для внутреннего использования.  <br/> |
   

