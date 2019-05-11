---
title: Таблица codecdescription
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: Таблица codecdescription назначение уникальных идентификаторов кодека соответствующему кодеку. Кодеки используется для кодирования цифровых сигналов для передачи и вещания, а затем для декодирования этих сигналов для воспроизведения. Эта таблица была введена в Microsoft Lync Server 2013
ms.openlocfilehash: 9881c802e332801d4990bf01894d5f8b68150fc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920105"
---
# <a name="codecdescription-table"></a>Таблица codecdescription
 
Таблица codecdescription назначение уникальных идентификаторов кодека соответствующему кодеку. Кодеки используется для кодирования цифровых сигналов для передачи и вещания, а затем для декодирования этих сигналов для воспроизведения. Эта таблица была введена в Microsoft Lync Server 2013
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |Уникальный идентификатор, назначенный кодеку.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Уникальный  <br/> |Уникальное описание кодека, соответствующего codecdescriptionkey.  <br/> |
   

