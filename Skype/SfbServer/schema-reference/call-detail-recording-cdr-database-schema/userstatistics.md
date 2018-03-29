---
title: Таблица userstatistics
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
ms.openlocfilehash: c4a7952eada01033836811555d2e448d13133a27
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="userstatistics-table"></a>Таблица userstatistics
 
Таблица userstatistics представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения об использовании отдельных пользователей системы. Эта таблица была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Идентификатор пользователя** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Время последнего пользователя войти в систему.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Время последней конференции, организованной пользователем.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Время последнего сбоя вызова был данный пользователь.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Время последнего пользователя сбоя вызова когда организатором конференции.  <br/> |
   

