---
title: Таблица Conference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Таблица Conference представляет собой вспомогательную таблицу. Каждая запись представляет один конференции или сеанса peer-to-peer.
ms.openlocfilehash: 0914e98aed4aea16e5301ccae454e925663454a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920168"
---
# <a name="conference-table"></a>Таблица Conference
 
Таблица Conference представляет собой вспомогательную таблицу. Каждая запись представляет один конференции или сеанса peer-to-peer.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту запись конференции.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |Уникальный  <br/> |URI конференции, если это конференции или DialogID при этом является peer-to-peer сеанса.  <br/> |
|**Контрольная сумма** <br/> |целое  <br/> |Индекс  <br/> |Контрольная сумма URI конференции. Этот параметр используется во внутренней сети.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

