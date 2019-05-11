---
title: Таблица Phones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Таблица Phones представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения о один телефонный номер, участвующих в вызовах VoIP с записями в базе данных.
ms.openlocfilehash: ba13a059e043cf2a18c41c28dce1a2a54e694b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930618"
---
# <a name="phones-table"></a>Таблица Phones
 
Таблица Phones представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения о один телефонный номер, участвующих в вызовах VoIP с записями в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий телефон.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Номер телефона.  <br/> |
|**NextUpdateTS** <br/> |даты и времени  <br/> ||Метка времени (только для внутреннего использования).  <br/> В этом поле было представлено в Microsoft Lync Server 2013.  <br/> |
   

