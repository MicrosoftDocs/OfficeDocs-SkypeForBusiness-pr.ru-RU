---
title: Таблица ErrorCategory в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Таблица ErrorCategory содержит понятное имя для каждого Скайп для диагностики классификации Business Server 2015. По умолчанию Скайп для Business Server 2015 используются следующих категорий:'
ms.openlocfilehash: b6226396302353b815138b41b7c19f170a0d6b4d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901089"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Таблица ErrorCategory в Скайп для Business Server 2015
 
Таблица ErrorCategory содержит понятное имя для каждого Скайп для диагностики классификации Business Server 2015. По умолчанию Скайп для Business Server 2015 используются следующих категорий:
  
- 0 — успешное завершение
    
- 1 — ожидаемый сбой
    
- 2 — неожиданный сбой
    
Эта таблица была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Идентификатор категории** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор для классификации.  <br/> |
|**Имя**. <br/> |nvarchar(256)  <br/> || Значение и понятное имя, присвоенное классификации. Допустимые значения: <br/>  0 — успешное завершение <br/>  1 — ожидаемый сбой <br/>  2 — неожиданный сбой <br/> |
   

