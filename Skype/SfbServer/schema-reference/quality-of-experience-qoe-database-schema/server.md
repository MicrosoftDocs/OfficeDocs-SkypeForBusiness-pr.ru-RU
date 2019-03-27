---
title: Таблица Servers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: В таблице Server представляет собой вспомогательную таблицу. Каждая запись представляет один сервер.
ms.openlocfilehash: 877743f5d589cd4fea34039786b33bd410069bb3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874310"
---
# <a name="server-table"></a>Таблица Servers
 
В таблице Server представляет собой вспомогательную таблицу. Каждая запись представляет один сервер. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сервер.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |Индекс  <br/> |Строка MAC-адреса.  <br/> |
|**ServerType** <br/> |целое  <br/> |Внешний  <br/> |1: сервер-посредник  <br/> 2: A / видеоконференций 16394: A пограничного service32769: шлюз  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||Пул, к которой принадлежит сервер. Применяется только для A / V Server конференц-связи.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

