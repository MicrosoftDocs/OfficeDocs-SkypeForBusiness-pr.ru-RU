---
title: Таблица CallPriorities в Skype для бизнеса Server 2015 г.
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
description: Таблица CallPriorities — это статическая таблица, в которую хранится список возможных приоритетов вызовов, таких как "чрезвычайная ситуация", "срочный" или "обычный".
ms.openlocfilehash: 73452cba57830ce08d7a4cf79ed78bf275101de0658ef006bc04efff44ee0d75
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296957"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Таблица CallPriorities в Skype для бизнеса Server 2015 г.
 
Таблица CallPriorities — это статическая таблица, в которую хранится список возможных приоритетов вызовов, таких как "чрезвычайная ситуация", "срочный" или "обычный".
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Приоритет** <br/> |nvarchar (256)  <br/> || Допустимые значения: <br/>  0 — неизвестно <br/>  1 . Несрочная <br/>  2 — обычный <br/>  3 — срочный <br/>  4 — экстренный <br/> |
   

