---
title: Таблица NetworkConnectionDetail
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: Таблица NetworkConnectionDetail сопоставляет типы сетевых подключений с идентификаторами используемыми в базе данных качества взаимодействия. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: cc1eb91d3c633ed9455a0476b613430dfa8e3d6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="networkconnectiondetail-table"></a>Таблица NetworkConnectionDetail
 
Таблица NetworkConnectionDetail сопоставляет типы сетевых подключений с идентификаторами используемыми в базе данных качества взаимодействия. Эта таблица была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор типа сетевого подключения.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Уникальный  <br/> |Тип сетевого подключения, соответствующий NetworkConnectionDetailKey. Доступны значения:  <br/> 0 — проводной сети  <br/> 1 — WiFi  <br/> 2 — Ethernet  <br/> 3 - MobileBB  <br/> 4 — другие  <br/> 5 — туннель  <br/> |
   

