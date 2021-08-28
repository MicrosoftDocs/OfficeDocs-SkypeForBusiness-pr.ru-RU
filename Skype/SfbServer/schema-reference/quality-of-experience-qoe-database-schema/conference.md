---
title: Таблица конференций
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Таблица Conference является вспомогательной. Каждая запись представляет одну конференцию или одноранговый сеанс.
ms.openlocfilehash: 3da2ed90cbb55e44d4eb4ff4902898eed6099f2e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609156"
---
# <a name="conference-table"></a>Таблица конференций
 
Таблица Conference является вспомогательной. Каждая запись представляет одну конференцию или одноранговый сеанс.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту запись конференции.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |уникальный  <br/> |URI для конференции или DialogID для однорангового сеанса.  <br/> |
|**Контрольная сумма** <br/> |int  <br/> |index  <br/> |Контрольная сумма URI конференции, предназначена для внутреннего использования.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

