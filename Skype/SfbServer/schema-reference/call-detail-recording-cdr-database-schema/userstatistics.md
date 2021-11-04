---
title: Таблица UserStatistics
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Таблица UserStatistics предназначена для поддержки. Каждая запись в таблице хранит сведения об использовании системы отдельным пользователем. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 01f002e1cba20200334f8696f9fb2c20c98e82c1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756452"
---
# <a name="userstatistics-table"></a>Таблица UserStatistics
 
Таблица UserStatistics предназначена для поддержки. Каждая запись в таблице хранит сведения об использовании системы отдельным пользователем. Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий данного пользователя.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Время последнего входа пользователя в систему.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Время последней конференции, организованной пользователем.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Время последнего сбоя вызова пользователя.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Время последнего сбоя вызова, когда организатором конференции был данный пользователь.  <br/> |
   

