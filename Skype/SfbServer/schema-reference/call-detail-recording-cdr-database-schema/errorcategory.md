---
title: Таблица ErrorCategory в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Таблица ErrorCategory содержит удобное имя для каждой диагностической классификации Skype для бизнеса Server 2015. По умолчанию Skype для бизнеса Server 2015 использует следующие классификации:'
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813149"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Таблица ErrorCategory в Skype для бизнеса Server 2015
 
Таблица ErrorCategory содержит удобное имя для каждой диагностической классификации Skype для бизнеса Server 2015. По умолчанию Skype для бизнеса Server 2015 использует следующие классификации:
  
- 0 — успешно
    
- 1 — ожидаемый сбой
    
- 2 — неожиданный сбой
    
Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор для классификации.  <br/> |
|**Название** <br/> |nvarchar(256)  <br/> || Значение и понятное имя, назначенные классификации. Допускаются следующие значения: <br/>  0 — успешно <br/>  1 — ожидаемый сбой <br/>  2 — неожиданный сбой <br/> |
   

