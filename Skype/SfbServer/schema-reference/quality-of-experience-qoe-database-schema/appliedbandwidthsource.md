---
title: Таблица AppliedBandwidthSource
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Таблица appliedbandwidthsource представляет собой вспомогательную таблицу. Каждая запись представляет один источник.
ms.openlocfilehash: 2fed25b6ca2218cb8b7300507b5c8258b2c29798
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212357"
---
# <a name="appliedbandwidthsource-table"></a>Таблица AppliedBandwidthSource
 
Таблица appliedbandwidthsource представляет собой вспомогательную таблицу. Каждая запись представляет один источник.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, определяющий источник.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Уникальный  <br/> |Это источник накладываемого ограничение пропускной способности. Этот параметр описывает где готовится к ограничение пропускной способности из (например, «Сервер политики», «ВКЛЮЧИТЬ сервер» или «Модальность»).  <br/> |
   

