---
title: Таблица пользователей
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
description: Таблица Пользователей — это вспомогательная таблица. Каждая запись в таблице хранит сведения об одном пользователе, вовлеченном в вызовы или сеансы, которые имеют записи в базе данных.
ms.openlocfilehash: 09706bf5b519ce85cd52898911ad6b878b6e5056246c47154f370ae8c75cc774
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302243"
---
# <a name="users-table"></a>Таблица пользователей
 
Таблица Пользователей — это вспомогательная таблица. Каждая запись в таблице хранит сведения об одном пользователе, вовлеченном в вызовы или сеансы, которые имеют записи в базе данных.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Штамп времени для внутреннего использования.  <br/> |
|**UserId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий данного пользователя.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> | <br/> |URI пользователя.  <br/> |
|**TenantId** <br/> |int  <br/> |Foreign  <br/> |ID клиента этого пользователя. Дополнительные сведения см. в таблице [Tenants.](tenants.md) <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |Тип URI этого пользователя. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
   

