---
title: Таблица CallPriorities в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Таблица CallPriorities — это статическая таблица, в которую хранится список возможных приоритетов вызовов, таких как "экстренный", "срочный" или "обычный".
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813439"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Таблица CallPriorities в Skype для бизнеса Server 2015
 
Таблица CallPriorities — это статическая таблица, в которую хранится список возможных приоритетов вызовов, таких как "экстренный", "срочный" или "обычный".
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Priority** <br/> |nvarchar(256)  <br/> || Допустимые значения: <br/>  0 — неизвестно <br/>  1 — несрочные <br/>  2 — обычный <br/>  3 — срочный <br/>  4 — экстренный <br/> |
   

