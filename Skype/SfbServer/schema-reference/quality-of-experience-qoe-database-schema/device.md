---
title: Таблица устройств
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Таблица "Устройство" представляет собой вспомогательную таблицу, в которой хранятся сведения о различных устройствах записи и отображения. Каждому устройству соответствует одна запись в таблице.
ms.openlocfilehash: 71a92ab0f73e844b4b58110dbb8c59650a26873a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763137"
---
# <a name="device-table"></a>Таблица устройств
 
Таблица "Устройство" представляет собой вспомогательную таблицу, в которой хранятся сведения о различных устройствах записи и отображения. Каждому устройству соответствует одна запись в таблице.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий это устройство.  <br/> |
|**DeviceName** <br/> |nvarchar (256)  <br/> |Значения DeviceName и DeviceType уникальны  <br/> |Имя устройства.  <br/> |
|**DeviceType** <br/> |bit  <br/> |Значения DeviceName и DeviceType уникальны  <br/> |Тип устройства. 1 - устройство записи, 0 - устройство отображения.  <br/> |
   

