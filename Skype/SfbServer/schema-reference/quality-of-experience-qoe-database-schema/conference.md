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
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Таблица Conference является вспомогательной. Каждая запись представляет одну конференцию или одноранговый сеанс.
ms.openlocfilehash: 6dfe60a28e8279f7b4c469c61cddc28912db261eedf4754588de4bd8f5852728
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309158"
---
# <a name="conference-table"></a>Таблица конференций
 
Таблица Conference является вспомогательной. Каждая запись представляет одну конференцию или одноранговый сеанс.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту запись конференции.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |уникальный  <br/> |URI для конференции или DialogID для однорангового сеанса.  <br/> |
|**Контрольная сумма** <br/> |int  <br/> |index  <br/> |Контрольная сумма URI конференции, предназначена для внутреннего использования.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

