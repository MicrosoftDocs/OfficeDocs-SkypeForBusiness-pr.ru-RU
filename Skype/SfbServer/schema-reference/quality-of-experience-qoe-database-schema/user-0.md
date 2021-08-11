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
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Таблица User является таблицей поддержки, в которой хранится список разных пользователей, участвовавших в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.
ms.openlocfilehash: 87e6e24ea9bf1073411eeb8c930e8e6fb509ae115242b529331aa43a25d5ac11
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329334"
---
# <a name="user-table"></a>Таблица пользователей
 
Таблица User является таблицей поддержки, в которой хранится список разных пользователей, участвовавших в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|**URI** <br/> |nvarchar (450)  <br/> |Уникальные  <br/> |Строка URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 — неизвестный тип URI.  <br/> 2 — URI пользователя.  <br/> 4 — URI конференции.  <br/> 8 — URI телефона.  <br/> |
|**TenantKey** <br/> |int  <br/> |Foreign  <br/> |Клиент пользователя, ссылается на таблицу клиентов.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Последняя метка времени, когда пользователь имел аудиовызов плохого качества.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

