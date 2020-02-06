---
title: Таблица SessionCorrelation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Таблица Сессионкоррелатион является вспомогательной таблицей. Каждая запись представляет собой один элемент CorrelationID, который используется для корреляции нескольких сеансов.
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805747"
---
# <a name="sessioncorrelation-table"></a>Таблица SessionCorrelation
 
Таблица Сессионкоррелатион является вспомогательной таблицей. Каждая запись представляет собой один элемент CorrelationID, который используется для корреляции нескольких сеансов. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Счет** <br/> |целое  <br/> |||
|**коррелатионкэй** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, показывающий этот сервер конференц-связи A/V.  <br/> |
|**Корреляци** <br/> |nvarchar(256)  <br/> |Повторя  <br/> |Коррелированные сеансы будут иметь одинаковый идентификатор корреляции.  <br/> |
|**некступдатетс** <br/> |datetime  <br/> | <br/> |Только для внутреннего использования.  <br/> |
   

