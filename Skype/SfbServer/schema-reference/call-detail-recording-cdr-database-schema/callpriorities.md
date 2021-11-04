---
title: Таблица CallPriorities в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 21924d712ff4ee658f757911ce168fe8b662357d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743215"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Таблица CallPriorities в Skype для бизнеса Server 2015 г.
 
Таблица CallPriorities — это статическая таблица, в которую хранится список возможных приоритетов вызовов, таких как "чрезвычайная ситуация", "срочный" или "обычный".
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Приоритет** <br/> |nvarchar (256)  <br/> || Допустимые значения: <br/>  0 — неизвестно <br/>  1 . Несрочная <br/>  2 — обычный <br/>  3 — срочный <br/>  4 — экстренный <br/> |
   

