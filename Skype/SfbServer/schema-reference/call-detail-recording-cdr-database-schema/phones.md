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
ms.localizationpriority: medium
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Таблица Телефоны — это вспомогательная таблица. Каждая запись в таблице хранит сведения об одном номере телефона, который участвует в звонках VoIP, которые имеют записи в базе данных.
ms.openlocfilehash: 37adaaa1885d91c84ee657c422b19debad294c01
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584863"
---
# <a name="phones-table"></a>Таблица телефонов
 
Таблица Телефоны — это вспомогательная таблица. Каждая запись в таблице хранит сведения об одном номере телефона, который участвует в звонках VoIP, которые имеют записи в базе данных.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот телефон.  <br/> |
|**PhoneUri** <br/> |nvarchar (450)  <br/> | <br/> |Телефон номер.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Штамп времени (только для внутреннего использования).  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
   

