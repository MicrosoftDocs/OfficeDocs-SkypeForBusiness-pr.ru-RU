---
title: Таблица MonitoredRegionLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Таблица monitoredregionlink представляет собой вспомогательную таблицу. Каждая запись представляет одну связь между двумя странах или регионах.
ms.openlocfilehash: 125f29a25b2ee039649dd47dcc405e208d0cd254
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920154"
---
# <a name="monitoredregionlink-table"></a>Таблица MonitoredRegionLink
 
Таблица monitoredregionlink представляет собой вспомогательную таблицу. Каждая запись представляет одну связь между двумя странах или регионах.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |целое  <br/> |Основной, внешний  <br/> |Ссылка из [Region table](region.md).  <br/> |
|**Region2Key** <br/> |целое  <br/> |Основной, внешний  <br/> |Ссылка из [Region table](region.md).  <br/> |
   

