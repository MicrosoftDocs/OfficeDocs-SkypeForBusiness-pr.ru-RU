---
title: Таблица телефонов
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 0dbe5065b4a0849b4538e77c05a846ed06f72da5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389811"
---
# <a name="phones-table"></a>Таблица телефонов
 
Таблица Телефоны — это вспомогательная таблица. Каждая запись в таблице хранит сведения об одном номере телефона, который участвует в звонках VoIP, которые имеют записи в базе данных.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот телефон.  <br/> |
|**PhoneUri** <br/> |nvarchar (450)  <br/> | <br/> |Номер телефона.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Штамп времени (только для внутреннего использования).  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
   

