---
title: Таблица MonitoredRegionLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Таблица monitoredregionlink представляет собой вспомогательную таблицу. Каждая запись представляет одну связь между двумя странах или регионах.
ms.openlocfilehash: 0df5cd8abe957ed952bdf656a67e1d423cc57f33
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884416"
---
# <a name="monitoredregionlink-table"></a>Таблица MonitoredRegionLink
 
Таблица monitoredregionlink представляет собой вспомогательную таблицу. Каждая запись представляет одну связь между двумя странах или регионах.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |целое  <br/> |Основной, внешний  <br/> |Ссылка из [Region table](region.md).  <br/> |
|**Region2Key** <br/> |целое  <br/> |Основной, внешний  <br/> |Ссылка из [Region table](region.md).  <br/> |
   

