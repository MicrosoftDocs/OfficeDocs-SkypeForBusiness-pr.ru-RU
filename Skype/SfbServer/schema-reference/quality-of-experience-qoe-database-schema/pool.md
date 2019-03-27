---
title: Таблица Pool
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Таблица Pool представляет собой вспомогательную таблицу, в которой хранятся сведения о различных пулов переднего плана. Каждая запись в таблице представляет один пул.
ms.openlocfilehash: ae8695316bdea6ba858bf9a4d334dc6075b99d50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874020"
---
# <a name="pool-table"></a>Таблица Pool
 
Таблица Pool представляет собой вспомогательную таблицу, в которой хранятся сведения о различных пулов переднего плана. Каждая запись в таблице представляет один пул.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот пул.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Уникальный  <br/> |Полное доменное имя пула.  <br/> |
   

