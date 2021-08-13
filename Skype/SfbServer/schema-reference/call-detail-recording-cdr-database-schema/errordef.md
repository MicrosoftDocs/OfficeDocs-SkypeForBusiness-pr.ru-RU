---
title: Таблица ErrorDef в Skype для бизнеса Server 2015 г.
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: В таблице ErrorDef хранится информация о каждом типе возможной ошибки. Каждая запись — это один тип ошибки.
ms.openlocfilehash: 428ce365de65be4d0bcd3776bfc069ffc9246fd869c54d819c6468f926c64351
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344608"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Таблица ErrorDef в Skype для бизнеса Server 2015 г.
 
В таблице ErrorDef хранится информация о каждом типе возможной ошибки. Каждая запись — это один тип ошибки.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер идентификации, определяющий этот тип ошибки.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Стандартный код ответа SIP, связанный с этой ошибкой.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft Diagnostic ID.  <br/> |
|**CallTypeId** <br/> |Целое  <br/> |Foreign  <br/> |Тип вызова. Дополнительные сведения см. в [таблице CallType Skype для бизнеса Server 2015](calltype.md) г. <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |Тип запроса с отказом.  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary (257)  <br/> | <br/> |Тип содержимого запроса с отказом.  <br/> Эти данные можно преобразовать в текстовый формат с помощью этого синтаксиса:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

