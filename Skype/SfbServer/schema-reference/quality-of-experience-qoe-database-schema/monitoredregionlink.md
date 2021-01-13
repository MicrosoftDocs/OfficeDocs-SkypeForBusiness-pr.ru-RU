---
title: Таблица MonitoredRegionLink
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Таблица MonitoredRegionLink является вспомогательной. Каждая запись представляет одно соединение между странами/регионами.
ms.openlocfilehash: f30ba249f89a2247e0e03c71fc97f05e69c59bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806349"
---
# <a name="monitoredregionlink-table"></a>Таблица MonitoredRegionLink
 
Таблица MonitoredRegionLink является вспомогательной. Каждая запись представляет одно соединение между странами/регионами.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Основной, Внешний  <br/> |Ссылка из [таблицы Region.](region.md)  <br/> |
|**Region2Key** <br/> |int  <br/> |Основной, Внешний  <br/> |Ссылка из [таблицы Region](region.md).  <br/> |
   

