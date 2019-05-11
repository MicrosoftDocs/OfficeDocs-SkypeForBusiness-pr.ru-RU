---
title: Таблица User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Таблица пользователей представляет собой вспомогательную таблицу, в которой хранится список различных пользователей, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет один пользователь.
ms.openlocfilehash: 426d272a5c8bee2fd37511edc62bcb3e1a0c533e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907040"
---
# <a name="user-table"></a>Таблица User
 
Таблица пользователей представляет собой вспомогательную таблицу, в которой хранится список различных пользователей, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет один пользователь.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Уникальный  <br/> |Строка URI.  <br/> |
|**URIType** <br/> |целое  <br/> ||1 — Неизвестный тип URI.  <br/> 2 — URI пользователя.  <br/> 4 — URI конференции.  <br/> 8 — URI телефона.  <br/> |
|**TenantKey** <br/> |целое  <br/> |Внешний  <br/> |Клиент пользователя, ссылается на таблицу клиентов.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Новейшие метка времени, когда пользователь имел аудиовызов плохого качества.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

