---
title: Таблица errordef в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: Таблица errordef хранит сведения о каждом типе, которая может возникнуть ошибка. Каждая запись является одного типа ошибки.
ms.openlocfilehash: cec601dad24dda522477bfcd7b1e80d0efc45799
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899069"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Таблица errordef в Скайп для Business Server 2015
 
Таблица errordef хранит сведения о каждом типе, которая может возникнуть ошибка. Каждая запись является одного типа ошибки.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Код ошибки** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий тип ошибки.  <br/> |
|**ResponseCode** <br/> |целое  <br/> | <br/> |Стандартный код ответа SIP, связанный с этой ошибкой.  <br/> |
|**MsDiagId** <br/> |целое  <br/> | <br/> |Диагностический идентификатор Майкрософт.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Внешний  <br/> |Тип вызова. [Таблица CallType в Скайп для Business Server 2015](calltype.md) для получения дополнительных сведений см. <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Тип запроса с отказом.  <br/> Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Тип содержимого запроса с отказом.  <br/> Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

