---
title: Таблица Device
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Таблица Device является вспомогательной таблицей, в которой хранятся сведения о различных устройствах захвата или рендеринге. Каждая запись в таблице представляет одно устройство.
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295008"
---
# <a name="device-table"></a>Таблица Device
 
Таблица Device является вспомогательной таблицей, в которой хранятся сведения о различных устройствах захвата или рендеринге. Каждая запись в таблице представляет одно устройство.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Девицекэй** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий это устройство.  <br/> |
|**Водит** <br/> |nvarchar(256)  <br/> |Имя_устройства + DeviceType является уникальным  <br/> |Имя устройства.  <br/> |
|**DeviceType** <br/> |бит  <br/> |Имя_устройства + DeviceType является уникальным  <br/> |Тип устройства. 1 — устройство захвата, 0 — устройство рендеринга.  <br/> |
   

