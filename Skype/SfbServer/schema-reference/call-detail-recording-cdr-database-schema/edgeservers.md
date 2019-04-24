---
title: Таблица edgeservers в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: Таблица edgeservers представляет собой вспомогательную таблицу. Каждая запись сохраняет сведения об одном пограничном сервере, задействованных в вызовы с записями в базе данных.
ms.openlocfilehash: 253190f23d130d12a1b4af701bf68922717d8da8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213139"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Таблица edgeservers в Скайп для Business Server 2015
 
Таблица edgeservers представляет собой вспомогательную таблицу. Каждая запись сохраняет сведения об одном пограничном сервере, задействованных в вызовы с записями в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот пограничный сервер.  <br/> |
|**Пограничный сервер** <br/> |nvarchar(256)  <br/> | <br/> |Имя пограничного сервера.  <br/> |
   

