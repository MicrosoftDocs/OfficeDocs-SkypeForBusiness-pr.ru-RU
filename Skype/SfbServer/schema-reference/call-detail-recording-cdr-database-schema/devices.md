---
title: Таблица Devices в Скайп для Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: В таблице устройств представляет собой вспомогательную таблицу. Каждая запись сохранение информации о одно устройство (стационарный телефон).
ms.openlocfilehash: c7a5a5933d4fe2e465faf039a8ac2ed2a65fa563
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Таблица Devices в Скайп для Business Server 2015
 
В таблице устройств представляет собой вспомогательную таблицу. Каждая запись сохранение информации о одно устройство (стационарный телефон).
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий версию оборудования.  <br/> |
|**ManufacturerId** <br/> |целое  <br/> |Внешний  <br/> |Производитель это устройство. В разделе [Таблица Manufacturers в Скайп для Business Server 2015](manufacturers.md) для получения дополнительных сведений. <br/> |
|**HardwareVersionId** <br/> |целое  <br/> |Внешний  <br/> |Версия оборудования это устройство. [Таблица hardwareversions в Скайп для Business Server 2015](hardwareversions.md) для получения дополнительных сведений см. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC-адрес  <br/> |
   

