---
title: Таблица User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: В таблице пользователей представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения о одного пользователя, участвующего в звонков или сеансах с записями в базе данных.
ms.openlocfilehash: fbe3ff7d2570f78cdf3b3418629fb9fd6209d944
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929989"
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
   

