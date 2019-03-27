---
title: Таблица codecdescription
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: Таблица codecdescription назначение уникальных идентификаторов кодека соответствующему кодеку. Кодеки используется для кодирования цифровых сигналов для передачи и вещания, а затем для декодирования этих сигналов для воспроизведения. Эта таблица была введена в Microsoft Lync Server 2013
ms.openlocfilehash: efda27afe9312c25add8be0f74364384aed53b3e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896500"
---
# <a name="codecdescription-table"></a>Таблица codecdescription
 
Таблица codecdescription назначение уникальных идентификаторов кодека соответствующему кодеку. Кодеки используется для кодирования цифровых сигналов для передачи и вещания, а затем для декодирования этих сигналов для воспроизведения. Эта таблица была введена в Microsoft Lync Server 2013
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |Уникальный идентификатор, назначенный кодеку.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Уникальный  <br/> |Уникальное описание кодека, соответствующего codecdescriptionkey.  <br/> |
   

