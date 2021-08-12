---
title: Таблица устройств в Skype для бизнеса Server 2015 г.
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
ms.openlocfilehash: eac31407de3f5a648ebe5f3819b2d7f3556e9bd6c2be930450e8e27700ead178
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295376"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Таблица устройств в Skype для бизнеса Server 2015 г.
 
Таблица устройств является вспомогательной. В каждой записи хранится информация об одном устройстве (стационарный телефон).
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий версию оборудования.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Foreign  <br/> |Производитель этого устройства. Дополнительные сведения см. в [таблице Manufacturers Skype для бизнеса Server 2015](manufacturers.md) г. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Foreign  <br/> |Версия оборудования этого устройства. Дополнительные сведения см. в таблице [HardwareVersions Skype для бизнеса Server 2015](hardwareversions.md) г. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC-адрес  <br/> |
   

