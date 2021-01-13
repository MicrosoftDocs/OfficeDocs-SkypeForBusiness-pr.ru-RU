---
title: Таблица Devices в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Таблица устройств является вспомогательной. В каждой записи хранится информация об одном устройстве (стационарный телефон).
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831819"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Таблица Devices в Skype для бизнеса Server 2015
 
Таблица устройств является вспомогательной. В каждой записи хранится информация об одном устройстве (стационарный телефон).
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий версию оборудования.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Внешняя  <br/> |Производитель этого устройства. Дополнительные сведения см. в таблице [Manufacturers в Skype для бизнеса Server 2015.](manufacturers.md) <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Внешняя  <br/> |Версия оборудования этого устройства. Дополнительные сведения см. в таблице [HardwareVersions в Skype для бизнеса Server 2015.](hardwareversions.md) <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC-адрес  <br/> |
   

