---
title: Таблица NetworkConnectionDetail
ms.reviewer: ''
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
ms.openlocfilehash: 6df2511c2dfee0158b4633be5dfa8549639cfc6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889058"
---
# <a name="networkconnectiondetail-table"></a>Таблица NetworkConnectionDetail
 
Таблица NetworkConnectionDetail сопоставляет типы сетевых подключений с идентификаторами используемыми в базе данных качества взаимодействия. Эта таблица была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор типа сетевого подключения.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Уникальный  <br/> |Тип сетевого подключения, соответствующий NetworkConnectionDetailKey. Допустимые значения:  <br/> 0 — проводной сети  <br/> 1 — WiFi  <br/> 2 — Ethernet  <br/> 3 - MobileBB  <br/> 4 — другие  <br/> 5 — туннель  <br/> |
   

