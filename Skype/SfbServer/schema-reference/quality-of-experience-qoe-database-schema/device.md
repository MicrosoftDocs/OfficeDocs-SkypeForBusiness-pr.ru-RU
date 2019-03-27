---
title: Таблица Device
ms.reviewer: ''
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
ms.openlocfilehash: 09af6ee11ebc821d123e847fbad812479d9d7bb0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885514"
---
# <a name="device-table"></a>Таблица Device
 
Таблица Device представляет собой вспомогательную таблицу, в которой хранятся сведения о различных захвата или отображать устройств. Каждая запись в таблице представляет одно устройство.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий это устройство.  <br/> |
|**Значения DeviceName** <br/> |nvarchar(256)  <br/> |Значения DeviceName и DeviceType уникальны  <br/> |Имя устройства.  <br/> |
|**DeviceType** <br/> |бит  <br/> |Значения DeviceName и DeviceType уникальны  <br/> |Тип устройства. 1 — для устройства захвата, 0 — это устройства обработки.  <br/> |
   

