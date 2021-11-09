---
title: Таблица CallPriorities в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Таблица CallPriorities — это статическая таблица, в которую хранится список возможных приоритетов вызовов, таких как "чрезвычайная ситуация", "срочный" или "обычный".
ms.openlocfilehash: ed31d55852f0b685429bd7fbf70cff1bf81d63ae
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845142"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Таблица CallPriorities в Skype для бизнеса Server 2015 г.
 
Таблица CallPriorities — это статическая таблица, в которую хранится список возможных приоритетов вызовов, таких как "чрезвычайная ситуация", "срочный" или "обычный".
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Приоритет** <br/> |nvarchar (256)  <br/> || Допустимые значения: <br/>  0 — неизвестно <br/>  1 . Несрочная <br/>  2 — обычный <br/>  3 — срочный <br/>  4 — экстренный <br/> |
   

