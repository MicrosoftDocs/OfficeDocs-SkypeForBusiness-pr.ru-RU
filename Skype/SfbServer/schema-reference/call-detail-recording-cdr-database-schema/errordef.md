---
title: Таблица ErrorDef в Skype для бизнеса Server 2015
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
description: В таблице ErrorDef хранится информация о каждом типе ошибки, которая может возникнуть. Каждая запись является одним типом ошибки.
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821729"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Таблица ErrorDef в Skype для бизнеса Server 2015
 
В таблице ErrorDef хранится информация о каждом типе ошибки, которая может возникнуть. Каждая запись является одним типом ошибки.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер ИД, определяющий этот тип ошибки.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Стандартный код ответа SIP, связанный с этой ошибкой.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |ИД диагностики Майкрософт.  <br/> |
|**CallTypeId** <br/> |Целое  <br/> |Внешняя  <br/> |Тип вызова. Дополнительные сведения см. в таблице [CallType в Skype для бизнеса Server 2015.](calltype.md) <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Тип запроса с отказом.  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Тип содержимого запроса с отказом.  <br/> Эти данные можно преобразовать в текстовый формат с помощью этого синтаксиса:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

