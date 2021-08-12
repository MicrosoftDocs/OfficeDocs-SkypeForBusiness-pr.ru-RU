---
title: Таблица ErrorCategory в Skype для бизнеса Server 2015 г.
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
description: 'Таблица ErrorCategory содержит удобное имя для каждой Skype для бизнеса Server диагностики 2015 года. По умолчанию Skype для бизнеса Server 2015 г. использует следующие классификации:'
ms.openlocfilehash: 68114e96e04ca8e2cb45fbb2b9ba0b3934df4e363700f8a872f05cb1aa0e8a37
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347774"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Таблица ErrorCategory в Skype для бизнеса Server 2015 г.
 
Таблица ErrorCategory содержит удобное имя для каждой Skype для бизнеса Server диагностики 2015 года. По умолчанию Skype для бизнеса Server 2015 г. использует следующие классификации:
  
- 0 — успешно
    
- 1 . Ожидаемый сбой
    
- 2 . Неожиданный сбой
    
Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор для классификации.  <br/> |
|**Название** <br/> |nvarchar (256)  <br/> || Значение и понятное имя, назначенные классификации. Допускаются следующие значения: <br/>  0 — успешно <br/>  1 . Ожидаемый сбой <br/>  2 . Неожиданный сбой <br/> |
   

