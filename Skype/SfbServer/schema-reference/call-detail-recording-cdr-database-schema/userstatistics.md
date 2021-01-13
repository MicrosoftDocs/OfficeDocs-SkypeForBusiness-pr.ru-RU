---
title: Таблица UserStatistics
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Таблица UserStatistics предназначена для поддержки. В каждой записи таблицы хранится информация об использовании системы отдельным пользователем. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813109"
---
# <a name="userstatistics-table"></a>Таблица UserStatistics
 
Таблица UserStatistics предназначена для поддержки. В каждой записи таблицы хранится информация об использовании системы отдельным пользователем. Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий данного пользователя.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Время последнего входа пользователя в систему.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Время последней конференции, организованной пользователем.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Время последнего сбоя вызова пользователя.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Время последнего сбоя вызова, когда организатором конференции был данный пользователь.  <br/> |
   

