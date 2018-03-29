---
title: Таблица Device
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Таблица Device представляет собой вспомогательную таблицу, в которой хранятся сведения о различных захвата или отображать устройств. Каждая запись в таблице представляет одно устройство.
ms.openlocfilehash: 346ea171b9a0c1b7a874b65a68b582c4167c57fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="device-table"></a>Таблица Device
 
Таблица Device представляет собой вспомогательную таблицу, в которой хранятся сведения о различных захвата или отображать устройств. Каждая запись в таблице представляет одно устройство.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий это устройство.  <br/> |
|**Значения DeviceName** <br/> |nvarchar(256)  <br/> |Значения DeviceName и DeviceType уникальны  <br/> |Имя устройства.  <br/> |
|**DeviceType** <br/> |бит  <br/> |Значения DeviceName и DeviceType уникальны  <br/> |Тип устройства. 1 — для устройства захвата, 0 — это устройства обработки.  <br/> |
   

