---
title: Таблица DeRegisterType в Skype для бизнеса Server 2015
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: Таблица DeRegisterType — это статическая таблица, в которую хранится список возможных типов регистрации пользователей, таких как "инициирован клиент", "срок действия регистрации истек" или "клиент перестал отвечать".
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816079"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Таблица DeRegisterType в Skype для бизнеса Server 2015
 
Таблица DeRegisterType — это статическая таблица, в которую хранится список возможных типов регистрации пользователей, таких как "инициализированный клиент", "срок действия регистрации истек" или "клиент перестал отвечать".
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Допустимые значения: <br/>  0 — неизвестно <br/>  1 — клиент инициировал отмену регистрации <br/>  2 — срок действия регистрации истек <br/>  3 — сбой клиента <br/>  4 — атрибуты пользователя изменены <br/>  5 — предпочтительный регистратор изменен <br/>  6 — устаревший клиент в режиме сохранения <br/> |
   

