---
title: Таблица ErrorCategory в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Таблица ErrorCategory содержит удобное имя для каждой Skype для бизнеса Server диагностики 2015 года. По умолчанию Skype для бизнеса Server 2015 г. использует следующие классификации:'
ms.openlocfilehash: 19fa265b337f293656473aa24c85bb5fc22008de
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743915"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Таблица ErrorCategory в Skype для бизнеса Server 2015 г.
 
Таблица ErrorCategory содержит удобное имя для каждой Skype для бизнеса Server диагностики 2015 года. По умолчанию Skype для бизнеса Server 2015 г. использует следующие классификации:
  
- 0 — успешно
    
- 1 . Ожидаемый сбой
    
- 2 . Неожиданный сбой
    
Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор для классификации.  <br/> |
|**Имя** <br/> |nvarchar (256)  <br/> || Значение и понятное имя, назначенные классификации. Допускаются следующие значения: <br/>  0 — успешно <br/>  1 . Ожидаемый сбой <br/>  2 . Неожиданный сбой <br/> |
   

