---
title: Таблица ErrorCategory в Скайп для Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Таблица ErrorCategory содержит понятное имя для каждого Скайп для диагностики классификации Business Server 2015. По умолчанию Скайп для Business Server 2015 используются следующих категорий:'
ms.openlocfilehash: 23df7ecb7e10dc104e6274edb762369ad539f8fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Таблица ErrorCategory в Скайп для Business Server 2015
 
Таблица ErrorCategory содержит понятное имя для каждого Скайп для диагностики классификации Business Server 2015. По умолчанию Скайп для Business Server 2015 используются следующих категорий:
  
- 0 — успешное завершение
    
- 1 — ожидаемый сбой
    
- 2 — неожиданный сбой
    
Эта таблица была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Идентификатор категории** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор для классификации.  <br/> |
|**Имя**. <br/> |nvarchar(256)  <br/> || Значение и понятное имя, присвоенное классификации. Доступны значения: <br/>  0 — успешное завершение <br/>  1 — ожидаемый сбой <br/>  2 — неожиданный сбой <br/> |
   

