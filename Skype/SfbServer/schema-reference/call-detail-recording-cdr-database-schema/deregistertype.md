---
title: Таблица DeRegisterType в Skype для бизнеса Server 2015 г.
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: 'Таблица DeRegisterType — это статическая таблица, в которую хранится список возможных типов дерегистрации пользователей, таких как "инициированный клиент", "истек срок регистрации" или "клиент перестал отвечать".'
---

# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Таблица DeRegisterType в Skype для бизнеса Server 2015 г.
 
Таблица DeRegisterType — это статическая таблица, в которую хранится список возможных типов дерегистрации пользователей, таких как "инициированный клиент", "истек срок регистрации" или "клиент перестал отвечать".
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar (256)  <br/> || Допустимые значения: <br/>  0 — неизвестно <br/>  1 — клиент инициировал отмену регистрации <br/>  2 — срок действия регистрации истек <br/>  3 . Клиент разбился <br/>  4 — атрибуты пользователя изменены <br/>  5 . Изменен предпочтительный регистратор <br/>  6 — устаревший клиент в режиме сохранения <br/> |
   

