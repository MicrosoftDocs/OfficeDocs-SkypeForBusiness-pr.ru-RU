---
title: Таблица устройств в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: bffa7bc59e2c1b52b3586d89f5f9c3828a569a26
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857246"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Таблица устройств в Skype для бизнеса Server 2015 г.
 
Таблица устройств является вспомогательной. В каждой записи хранится информация об одном устройстве (стационарный телефон).
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий версию оборудования.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Foreign  <br/> |Производитель этого устройства. Дополнительные сведения см. в [таблице Manufacturers Skype для бизнеса Server 2015](manufacturers.md) г. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Foreign  <br/> |Версия оборудования этого устройства. Дополнительные сведения см. в таблице [HardwareVersions Skype для бизнеса Server 2015](hardwareversions.md) г. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC-адрес  <br/> |
   

