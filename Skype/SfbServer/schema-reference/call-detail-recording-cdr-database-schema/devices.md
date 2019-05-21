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
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Таблица "устройства" является вспомогательной таблицей. Каждая запись хранит информацию об одном устройстве (стационарном телефоне).
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296380"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Таблица "устройства" в Skype для бизнеса Server 2015
 
Таблица "устройства" является вспомогательной таблицей. Каждая запись хранит информацию об одном устройстве (стационарном телефоне).
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Устройства** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту аппаратную версию.  <br/> |
|**ManufacturerId** <br/> |целое  <br/> |Другом  <br/> |Производитель этого устройства. Более подробную информацию вы увидите [в таблице изготовителей в Skype для бизнеса Server 2015](manufacturers.md) . <br/> |
|**Хардвареверсионид** <br/> |целое  <br/> |Другом  <br/> |Аппаратная версия этого устройства. Для получения дополнительных сведений ознакомьтесь с [таблицей хардвареверсионс в Skype для бизнеса Server 2015](hardwareversions.md) . <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC-адрес  <br/> |
   

