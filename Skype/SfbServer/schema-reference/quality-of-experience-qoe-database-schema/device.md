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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Таблица Device является вспомогательной таблицей, в которой хранятся сведения о различных устройствах захвата или рендеринге. Каждая запись в таблице представляет одно устройство.
ms.openlocfilehash: 93e6b2215fa1e20b930d678c45f10e26feffd351
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810157"
---
# <a name="device-table"></a>Таблица Device
 
Таблица Device является вспомогательной таблицей, в которой хранятся сведения о различных устройствах захвата или рендеринге. Каждая запись в таблице представляет одно устройство.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**девицекэй** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий это устройство.  <br/> |
|**Водит** <br/> |nvarchar(256)  <br/> |Имя_устройства + DeviceType является уникальным  <br/> |Имя устройства.  <br/> |
|**DeviceType** <br/> |бит  <br/> |Имя_устройства + DeviceType является уникальным  <br/> |Тип устройства. 1 — устройство захвата, 0 — устройство рендеринга.  <br/> |
   

