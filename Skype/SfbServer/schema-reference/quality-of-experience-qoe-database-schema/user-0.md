---
title: Таблица User
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Таблица пользователей представляет собой вспомогательную таблицу, в которой хранится список различных пользователей, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет один пользователь.
ms.openlocfilehash: 3261133b8c36fe96fd847c075dce0be2a903c417
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="user-table"></a>Таблица User
 
Таблица пользователей представляет собой вспомогательную таблицу, в которой хранится список различных пользователей, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет один пользователь.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Уникальный  <br/> |Строка URI.  <br/> |
|**URIType** <br/> |целое  <br/> ||1 — Неизвестный тип URI.  <br/> 2 — URI пользователя.  <br/> 4 — URI конференции.  <br/> 8 — URI телефона.  <br/> |
|**TenantKey** <br/> |целое  <br/> |Внешний  <br/> |Клиент пользователя, ссылается на таблицу клиентов.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Новейшие метка времени, когда пользователь имел аудиовызов плохого качества.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

