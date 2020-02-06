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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Таблица конференции — это вспомогательная таблица. Каждая запись представляет одну конференцию или одноранговый сеанс.
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810307"
---
# <a name="conference-table"></a>Таблица Conference
 
Таблица конференции — это вспомогательная таблица. Каждая запись представляет одну конференцию или одноранговый сеанс.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**конференцекэй** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту запись конференции.  <br/> |
|**конфури** <br/> |nvarchar (450)  <br/> |повторя  <br/> |Универсальный код ресурса (URI) для Конференции, если это конференция, или Диалогид, если это одноранговый сеанс.  <br/> |
|**Счет** <br/> |целое  <br/> |индекса  <br/> |Контрольная сумма URI конференции. Используется для внутренних целей.  <br/> |
|**некступдатетс** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

