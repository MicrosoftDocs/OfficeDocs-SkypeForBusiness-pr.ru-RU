---
title: Таблица CallPriorities в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Таблица CallPriorities — это статическая таблица, в которой хранится список возможных приоритетов вызовов, такие как «emergency», «срочно» или «normal».
ms.openlocfilehash: faf4e7f04d7a63b096cb2369c21916e5fcb71a24
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882992"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Таблица CallPriorities в Скайп для Business Server 2015
 
Таблица CallPriorities — это статическая таблица, в которой хранится список возможных приоритетов вызовов, такие как «emergency», «срочно» или «normal».
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Priority** <br/> |nvarchar(256)  <br/> || Допускаются следующие значения: <br/>  0 — Неизвестный <br/>  1 — не срочный <br/>  2 — Normal <br/>  3 - срочным <br/>  4 - аварийного <br/> |
   

