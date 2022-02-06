---
title: Таблица устройств в Skype для бизнеса Server 2015 г.
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Таблица устройств является вспомогательной. В каждой записи хранится информация об одном устройстве (стационарный телефон).
---

# <a name="devices-table-in-skype-for-business-server-2015"></a>Таблица устройств в Skype для бизнеса Server 2015 г.
 
Таблица устройств является вспомогательной. В каждой записи хранится информация об одном устройстве (стационарный телефон).
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий версию оборудования.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Foreign  <br/> |Производитель этого устройства. Дополнительные [сведения см. в таблице Manufacturers Skype для бизнеса Server 2015](manufacturers.md). <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Foreign  <br/> |Версия оборудования этого устройства. Дополнительные сведения см. в таблице [HardwareVersions Skype для бизнеса Server 2015](hardwareversions.md) г. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC-адрес  <br/> |
   

