---
title: Таблица "устройства" в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Таблица "устройства" является вспомогательной таблицей. Каждая запись хранит информацию об одном устройстве (стационарном телефоне).
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815287"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Таблица "устройства" в Skype для бизнеса Server 2015
 
Таблица "устройства" является вспомогательной таблицей. Каждая запись хранит информацию об одном устройстве (стационарном телефоне).
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Устройства** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту аппаратную версию.  <br/> |
|**ManufacturerId** <br/> |целое  <br/> |Другом  <br/> |Производитель этого устройства. Более подробную информацию вы увидите [в таблице изготовителей в Skype для бизнеса Server 2015](manufacturers.md) . <br/> |
|**хардвареверсионид** <br/> |целое  <br/> |Другом  <br/> |Аппаратная версия этого устройства. Для получения дополнительных сведений ознакомьтесь с [таблицей хардвареверсионс в Skype для бизнеса Server 2015](hardwareversions.md) . <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC-адрес  <br/> |
   

