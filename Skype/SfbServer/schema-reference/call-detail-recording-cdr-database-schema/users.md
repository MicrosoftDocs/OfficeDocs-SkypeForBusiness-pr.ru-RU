---
title: Таблица User
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: В таблице пользователей представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения о одного пользователя, участвующего в звонков или сеансах с записями в базе данных.
ms.openlocfilehash: 3929ba33737c107ee60ec1e31beebb1addbb2e3f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212742"
---
# <a name="users-table"></a>Таблица User
 
В таблице пользователей представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения о одного пользователя, участвующего в звонков или сеансах с записями в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Метка времени для внутреннего использования.  <br/> |
|**Идентификатор пользователя** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI пользователя.  <br/> |
|**TenantId** <br/> |целое  <br/> |Внешний  <br/> |Идентификатор клиента этого пользователя. В [таблице клиентов](tenants.md) для получения дополнительных сведений см. <br/> |
|**UriTypeId** <br/> |целое  <br/> |Внешний  <br/> |Тип URI этого пользователя. В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см. <br/> |
   

