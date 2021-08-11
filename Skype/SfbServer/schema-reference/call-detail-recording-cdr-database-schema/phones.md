---
title: Таблица телефонов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Таблица Телефоны — это вспомогательная таблица. Каждая запись в таблице хранит сведения об одном номере телефона, который участвует в звонках VoIP, которые имеют записи в базе данных.
ms.openlocfilehash: 938e00267f5f356c646d363033ef9a8917b910261f873637c0f6b3a6b9ff8742
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329463"
---
# <a name="phones-table"></a>Таблица телефонов
 
Таблица Телефоны — это вспомогательная таблица. Каждая запись в таблице хранит сведения об одном номере телефона, который участвует в звонках VoIP, которые имеют записи в базе данных.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот телефон.  <br/> |
|**PhoneUri** <br/> |nvarchar (450)  <br/> | <br/> |Телефон номер.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Штамп времени (только для внутреннего использования).  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
   

