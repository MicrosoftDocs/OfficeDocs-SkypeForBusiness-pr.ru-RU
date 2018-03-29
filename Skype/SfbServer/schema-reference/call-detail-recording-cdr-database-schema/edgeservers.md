---
title: Таблица edgeservers в Скайп для Business Server 2015
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
ms.openlocfilehash: 581dfcb6bbd3b5088af2bbc27a580d791b9ef8f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Таблица edgeservers в Скайп для Business Server 2015
 
Таблица edgeservers представляет собой вспомогательную таблицу. Каждая запись сохраняет сведения об одном пограничном сервере, задействованных в вызовы с записями в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот пограничный сервер.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> | <br/> |Имя пограничного сервера.  <br/> |
   

