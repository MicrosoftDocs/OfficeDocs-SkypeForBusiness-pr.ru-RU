---
title: Таблица конференций
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 8d47cd6c67d6d8d17d187353b8b15d79b38acab3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827372"
---
# <a name="conference-table"></a>Таблица конференций
 
Таблица Conference является вспомогательной. Каждая запись представляет одну конференцию или одноранговый сеанс.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту запись конференции.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |уникальный  <br/> |URI для конференции или DialogID для однорангового сеанса.  <br/> |
|**Контрольная сумма** <br/> |int  <br/> |index  <br/> |Контрольная сумма URI конференции, предназначена для внутреннего использования.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

