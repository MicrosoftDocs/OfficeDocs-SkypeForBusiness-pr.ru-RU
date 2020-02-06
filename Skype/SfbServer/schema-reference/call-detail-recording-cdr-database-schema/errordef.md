---
title: Таблица Еррордеф в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: В таблице Еррордеф хранятся сведения о каждом типе ошибки, которые могут возникать. Каждая запись имеет один тип ошибки.
ms.openlocfilehash: f686692bee334c0927b6e8342cfb7152b3e54f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815237"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Таблица Еррордеф в Skype для бизнеса Server 2015
 
В таблице Еррордеф хранятся сведения о каждом типе ошибки, которые могут возникать. Каждая запись имеет один тип ошибки.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**еррорид** <br/> |целое  <br/> |Primary  <br/> |Уникальный ИДЕНТИФИКАЦИОНный номер, показывающий этот тип ошибки.  <br/> |
|**респонсекоде** <br/> |целое  <br/> | <br/> |Стандартный код ответа SIP, связанный с этой ошибкой.  <br/> |
|**мсдиагид** <br/> |целое  <br/> | <br/> |Идентификатор диагностики (Майкрософт).  <br/> |
|**каллтипеид** <br/> |Типом  <br/> |Другом  <br/> |Тип звонка. Для получения дополнительных сведений ознакомьтесь с [таблицей каллтипе в Skype для бизнеса Server 2015](calltype.md) . <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |Тип запроса, который завершился сбоем.  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**Контента** <br/> |varbinary (257)  <br/> | <br/> |Тип контента запроса, который завершился сбоем.  <br/> Эти данные можно преобразовать в текстовый формат с помощью синтаксиса:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

