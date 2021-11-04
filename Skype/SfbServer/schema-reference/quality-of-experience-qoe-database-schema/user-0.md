---
title: Таблица пользователей
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: b8a2fc4775fe36f710cb54c937261a806eef2054
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776009"
---
# <a name="user-table"></a>Таблица пользователей
 
Таблица User является таблицей поддержки, в которой хранится список разных пользователей, участвовавших в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|**URI** <br/> |nvarchar (450)  <br/> |Уникальные  <br/> |Строка URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 — неизвестный тип URI.  <br/> 2 — URI пользователя.  <br/> 4 — URI конференции.  <br/> 8 — URI телефона.  <br/> |
|**TenantKey** <br/> |int  <br/> |Foreign  <br/> |Клиент пользователя, ссылается на таблицу клиентов.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Последняя метка времени, когда пользователь имел аудиовызов плохого качества.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

