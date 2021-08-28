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
ms.localizationpriority: medium
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: В таблице ErrorDef хранится информация о каждом типе возможной ошибки. Каждая запись — это один тип ошибки.
ms.openlocfilehash: 4d10e5c8a83e486fe16808a3cf5f38f7ffd15937
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615535"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Таблица ErrorDef в Skype для бизнеса Server 2015 г.
 
В таблице ErrorDef хранится информация о каждом типе возможной ошибки. Каждая запись — это один тип ошибки.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер идентификации, определяющий этот тип ошибки.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Стандартный код ответа SIP, связанный с этой ошибкой.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft Diagnostic ID.  <br/> |
|**CallTypeId** <br/> |Целое  <br/> |Foreign  <br/> |Тип вызова. Дополнительные сведения см. в [таблице CallType Skype для бизнеса Server 2015](calltype.md) г. <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |Тип запроса с отказом.  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary (257)  <br/> | <br/> |Тип содержимого запроса с отказом.  <br/> Эти данные можно преобразовать в текстовый формат с помощью этого синтаксиса:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

