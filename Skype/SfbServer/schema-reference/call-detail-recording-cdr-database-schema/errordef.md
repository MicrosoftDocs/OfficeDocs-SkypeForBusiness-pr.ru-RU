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
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: В таблице Еррордеф хранятся сведения о каждом типе ошибки, которые могут возникать. Каждая запись имеет один тип ошибки.
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296282"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Таблица Еррордеф в Skype для бизнеса Server 2015
 
В таблице Еррордеф хранятся сведения о каждом типе ошибки, которые могут возникать. Каждая запись имеет один тип ошибки.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Еррорид** <br/> |целое  <br/> |Primary  <br/> |Уникальный ИДЕНТИФИКАЦИОНный номер, показывающий этот тип ошибки.  <br/> |
|**Респонсекоде** <br/> |целое  <br/> | <br/> |Стандартный код ответа SIP, связанный с этой ошибкой.  <br/> |
|**Мсдиагид** <br/> |целое  <br/> | <br/> |Идентификатор диагностики (Майкрософт).  <br/> |
|**Каллтипеид** <br/> |Типом  <br/> |Другом  <br/> |Тип звонка. Для получения дополнительных сведений ознакомьтесь с [таблицей каллтипе в Skype для бизнеса Server 2015](calltype.md) . <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |Тип запроса, который завершился сбоем.  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**Контента** <br/> |varbinary (257)  <br/> | <br/> |Тип контента запроса, который завершился сбоем.  <br/> Эти данные можно преобразовать в текстовый формат с помощью синтаксиса:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

