---
title: Таблица edgeservers в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: Таблица edgeservers представляет собой вспомогательную таблицу. Каждая запись сохраняет сведения об одном пограничном сервере, задействованных в вызовы с записями в базе данных.
ms.openlocfilehash: a55a72f9a98dda0295256803a7f9318116ecf969
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901054"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Таблица edgeservers в Скайп для Business Server 2015
 
Таблица edgeservers представляет собой вспомогательную таблицу. Каждая запись сохраняет сведения об одном пограничном сервере, задействованных в вызовы с записями в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот пограничный сервер.  <br/> |
|**Пограничный сервер** <br/> |nvarchar(256)  <br/> | <br/> |Имя пограничного сервера.  <br/> |
   

