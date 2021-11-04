---
title: Таблица конференций
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Таблица Conference является вспомогательной. Каждая запись представляет одну конференцию или одноранговый сеанс.
ms.openlocfilehash: b5129fec73658d86fdb8d5cd7dd5c387cdadf4f9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763217"
---
# <a name="conference-table"></a>Таблица конференций
 
Таблица Conference является вспомогательной. Каждая запись представляет одну конференцию или одноранговый сеанс.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту запись конференции.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |уникальный  <br/> |URI для конференции или DialogID для однорангового сеанса.  <br/> |
|**Контрольная сумма** <br/> |int  <br/> |index  <br/> |Контрольная сумма URI конференции, предназначена для внутреннего использования.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

