---
title: Таблица Conference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Таблица конференции — это вспомогательная таблица. Каждая запись представляет одну конференцию или одноранговый сеанс.
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295015"
---
# <a name="conference-table"></a>Таблица Conference
 
Таблица конференции — это вспомогательная таблица. Каждая запись представляет одну конференцию или одноранговый сеанс.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Конференцекэй** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту запись конференции.  <br/> |
|**Конфури** <br/> |nvarchar (450)  <br/> |повторя  <br/> |Универсальный код ресурса (URI) для Конференции, если это конференция, или Диалогид, если это одноранговый сеанс.  <br/> |
|**Счет** <br/> |целое  <br/> |индекса  <br/> |Контрольная сумма URI конференции. Используется для внутренних целей.  <br/> |
|**Некступдатетс** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

