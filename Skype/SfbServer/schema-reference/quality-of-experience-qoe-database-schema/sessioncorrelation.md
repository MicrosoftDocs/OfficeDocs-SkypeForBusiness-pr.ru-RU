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
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Таблица Сессионкоррелатион является вспомогательной таблицей. Каждая запись представляет собой один элемент CorrelationID, который используется для корреляции нескольких сеансов.
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294658"
---
# <a name="sessioncorrelation-table"></a>Таблица SessionCorrelation
 
Таблица Сессионкоррелатион является вспомогательной таблицей. Каждая запись представляет собой один элемент CorrelationID, который используется для корреляции нескольких сеансов. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Счет** <br/> |целое  <br/> |||
|**Коррелатионкэй** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, показывающий этот сервер конференц-связи A/V.  <br/> |
|**Корреляци** <br/> |nvarchar(256)  <br/> |Повторя  <br/> |Коррелированные сеансы будут иметь одинаковый идентификатор корреляции.  <br/> |
|**Некступдатетс** <br/> |datetime  <br/> | <br/> |Только для внутреннего использования.  <br/> |
   

