---
title: Таблица Phones
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
description: Таблица Phones является вспомогательной. В каждой записи таблицы хранится информация об одном телефонном номере, который участвует в вызовах VoIP, в базе данных которых есть записи.
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823269"
---
# <a name="phones-table"></a>Таблица Phones
 
Таблица Phones является вспомогательной. В каждой записи таблицы хранится информация об одном телефонном номере, задействованном в вызовах VoIP, которые имеют записи в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот телефон.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Номер телефона.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Отметка времени (только для внутреннего использования).  <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
   

