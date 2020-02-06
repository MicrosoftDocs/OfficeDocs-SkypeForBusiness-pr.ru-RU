---
title: Таблица Каллприоритиес в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Таблица Каллприоритиес — это статическая таблица, в которой хранится список возможных приоритетов звонков, например "экстренная", "срочно" или "Обычная".
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815447"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Таблица Каллприоритиес в Skype для бизнеса Server 2015
 
Таблица Каллприоритиес — это статическая таблица, в которой хранится список возможных приоритетов звонков, например "экстренная", "срочно" или "Обычная".
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**приоритид** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Priority** <br/> |nvarchar(256)  <br/> || Допустимые значения: <br/>  0 — неизвестно <br/>  1-срочный <br/>  2-обычный <br/>  3-Срочный <br/>  4-экстренная ситуация <br/> |
   

