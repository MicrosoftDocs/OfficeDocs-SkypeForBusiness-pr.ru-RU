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
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Таблица Каллприоритиес — это статическая таблица, в которой хранится список возможных приоритетов звонков, например "экстренная", "срочно" или "Обычная".
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296569"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Таблица Каллприоритиес в Skype для бизнеса Server 2015
 
Таблица Каллприоритиес — это статическая таблица, в которой хранится список возможных приоритетов звонков, например "экстренная", "срочно" или "Обычная".
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Приоритид** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Priority** <br/> |nvarchar(256)  <br/> || Допустимые значения: <br/>  0 — неизвестно <br/>  1-срочный <br/>  2-обычный <br/>  3-Срочный <br/>  4-экстренная ситуация <br/> |
   

