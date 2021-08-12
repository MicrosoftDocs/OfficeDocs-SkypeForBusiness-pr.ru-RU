---
title: Таблица устройств
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Таблица "Устройство" представляет собой вспомогательную таблицу, в которой хранятся сведения о различных устройствах записи и отображения. Каждому устройству соответствует одна запись в таблице.
ms.openlocfilehash: d060ec010cc67ea45fb2f7c58ccc574a7bdbc4ea566342943f7a8f587a9676f5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347734"
---
# <a name="device-table"></a>Таблица устройств
 
Таблица "Устройство" представляет собой вспомогательную таблицу, в которой хранятся сведения о различных устройствах записи и отображения. Каждому устройству соответствует одна запись в таблице.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий это устройство.  <br/> |
|**DeviceName** <br/> |nvarchar (256)  <br/> |Значения DeviceName и DeviceType уникальны  <br/> |Имя устройства.  <br/> |
|**DeviceType** <br/> |bit  <br/> |Значения DeviceName и DeviceType уникальны  <br/> |Тип устройства. 1 - устройство записи, 0 - устройство отображения.  <br/> |
   

