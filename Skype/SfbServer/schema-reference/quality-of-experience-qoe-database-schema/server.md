---
title: Таблица Servers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: В таблице Server представляет собой вспомогательную таблицу. Каждая запись представляет один сервер.
ms.openlocfilehash: c0031e7181bb39895edadc40748f61626621f00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920133"
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
   

