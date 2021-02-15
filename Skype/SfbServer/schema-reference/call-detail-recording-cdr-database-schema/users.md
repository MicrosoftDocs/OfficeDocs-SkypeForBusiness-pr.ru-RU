---
title: Таблица Users
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Таблица Users является вспомогательной. В каждой записи таблицы хранится информация об одном пользователе, вовлеченном в вызовы или сеансы с записями в базе данных.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831619"
---
# <a name="users-table"></a>Таблица Users
 
Таблица Users является вспомогательной. В каждой записи таблицы хранится информация об одном пользователе, вовлеченном в вызовы или сеансы с записями в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Отметка времени для внутреннего использования.  <br/> |
|**UserId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий данного пользователя.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI пользователя.  <br/> |
|**TenantId** <br/> |int  <br/> |Внешняя  <br/> |ИД клиента этого пользователя. Дополнительные [сведения см.](tenants.md) в таблице Tenants. <br/> |
|**UriTypeId** <br/> |int  <br/> |Внешняя  <br/> |Тип URI этого пользователя. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
   

