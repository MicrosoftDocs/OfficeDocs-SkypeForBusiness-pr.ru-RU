---
title: Таблица userstatistics
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Таблица userstatistics представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения об использовании отдельных пользователей системы. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 45f34a1e8905d19b5ce48d94824591f25ec1ef28
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883597"
---
# <a name="userstatistics-table"></a>Таблица userstatistics
 
Таблица userstatistics представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения об использовании отдельных пользователей системы. Эта таблица была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Идентификатор пользователя** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Время последнего пользователя войти в систему.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Время последней конференции, организованной пользователем.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Время последнего сбоя вызова был данный пользователь.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Время последнего пользователя сбоя вызова когда организатором конференции.  <br/> |
   

