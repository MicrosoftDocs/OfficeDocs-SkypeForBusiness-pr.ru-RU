---
title: Таблица устройств
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: 'Таблица "Устройство" представляет собой вспомогательную таблицу, в которой хранятся сведения о различных устройствах записи и отображения. Каждому устройству соответствует одна запись в таблице.'
---

# <a name="device-table"></a>Таблица устройств
 
Таблица "Устройство" представляет собой вспомогательную таблицу, в которой хранятся сведения о различных устройствах записи и отображения. Каждому устройству соответствует одна запись в таблице.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий это устройство.  <br/> |
|**DeviceName** <br/> |nvarchar (256)  <br/> |Значения DeviceName и DeviceType уникальны  <br/> |Имя устройства.  <br/> |
|**DeviceType** <br/> |bit  <br/> |Значения DeviceName и DeviceType уникальны  <br/> |Тип устройства. 1 - устройство записи, 0 - устройство отображения.  <br/> |
   

