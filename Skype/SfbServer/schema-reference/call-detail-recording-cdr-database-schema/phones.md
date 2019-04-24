---
title: Таблица Phones
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Таблица Phones представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения о один телефонный номер, участвующих в вызовах VoIP с записями в базе данных.
ms.openlocfilehash: 733adec46e948c3b7f1d804f57011110355078f4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212889"
---
# <a name="phones-table"></a>Таблица Phones
 
Таблица Phones представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения о один телефонный номер, участвующих в вызовах VoIP с записями в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий телефон.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Номер телефона.  <br/> |
|**NextUpdateTS** <br/> |даты и времени  <br/> ||Метка времени (только для внутреннего использования).  <br/> В этом поле было представлено в Microsoft Lync Server 2013.  <br/> |
   

