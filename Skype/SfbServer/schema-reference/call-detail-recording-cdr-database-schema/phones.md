---
title: Таблица телефонов
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Таблица Телефоны — это вспомогательная таблица. Каждая запись в таблице хранит сведения об одном номере телефона, который участвует в звонках VoIP, которые имеют записи в базе данных.
ms.openlocfilehash: 249b2a08e0751b6e8746f2da27a13e1151c375f7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836107"
---
# <a name="phones-table"></a>Таблица телефонов
 
Таблица Телефоны — это вспомогательная таблица. Каждая запись в таблице хранит сведения об одном номере телефона, который участвует в звонках VoIP, которые имеют записи в базе данных.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот телефон.  <br/> |
|**PhoneUri** <br/> |nvarchar (450)  <br/> | <br/> |Телефон номер.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Штамп времени (только для внутреннего использования).  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
   

