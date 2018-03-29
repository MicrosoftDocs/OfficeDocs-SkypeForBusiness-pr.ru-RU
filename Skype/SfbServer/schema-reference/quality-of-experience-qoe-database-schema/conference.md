---
title: Таблица Conference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Таблица Conference представляет собой вспомогательную таблицу. Каждая запись представляет один конференции или сеанса peer-to-peer.
ms.openlocfilehash: 0390f1f9da264ab5269c7bfdcb4a86c08097b835
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="conference-table"></a>Таблица Conference
 
Таблица Conference представляет собой вспомогательную таблицу. Каждая запись представляет один конференции или сеанса peer-to-peer.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту запись конференции.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |Уникальный  <br/> |URI конференции, если это конференции или DialogID при этом является peer-to-peer сеанса.  <br/> |
|**Контрольная сумма** <br/> |целое  <br/> |Индекс  <br/> |Контрольная сумма URI конференции. Этот параметр используется во внутренней сети.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

