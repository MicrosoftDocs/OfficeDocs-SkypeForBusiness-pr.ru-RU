---
title: Таблица пользователей
ms.reviewer: ''
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Таблица Пользователей — это вспомогательная таблица. Каждая запись в таблице хранит сведения об одном пользователе, вовлеченном в вызовы или сеансы, которые имеют записи в базе данных.
ms.openlocfilehash: 66f3e1247d29969ecef36a5d6247510b5eae022c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389781"
---
# <a name="users-table"></a>Таблица пользователей
 
Таблица Пользователей — это вспомогательная таблица. Каждая запись в таблице хранит сведения об одном пользователе, вовлеченном в вызовы или сеансы, которые имеют записи в базе данных.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Штамп времени для внутреннего использования.  <br/> |
|**UserId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий данного пользователя.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> | <br/> |URI пользователя.  <br/> |
|**TenantId** <br/> |int  <br/> |Foreign  <br/> |ID клиента этого пользователя. Дополнительные [сведения см. в таблице Tenants](tenants.md) . <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |Тип URI этого пользователя. Дополнительные сведения [см. в таблице UriTypes](uritypes.md) . <br/> |
   

