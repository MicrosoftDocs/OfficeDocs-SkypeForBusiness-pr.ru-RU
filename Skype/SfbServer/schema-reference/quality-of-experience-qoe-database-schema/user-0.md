---
title: Таблица пользователей
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Таблица User является таблицей поддержки, в которой хранится список разных пользователей, участвовавших в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.
ms.openlocfilehash: 4278c3649ea55db969295f4068fcfe268a7258bb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582553"
---
# <a name="user-table"></a>Таблица пользователей
 
Таблица User является таблицей поддержки, в которой хранится список разных пользователей, участвовавших в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|**URI** <br/> |nvarchar (450)  <br/> |Уникальные  <br/> |Строка URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 — неизвестный тип URI.  <br/> 2 — URI пользователя.  <br/> 4 — URI конференции.  <br/> 8 — URI телефона.  <br/> |
|**TenantKey** <br/> |int  <br/> |Foreign  <br/> |Клиент пользователя, ссылается на таблицу клиентов.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Последняя метка времени, когда пользователь имел аудиовызов плохого качества.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

