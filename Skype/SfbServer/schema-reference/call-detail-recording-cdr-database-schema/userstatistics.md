---
title: Таблица UserStatistics
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Таблица UserStatistics предназначена для поддержки. Каждая запись в таблице хранит сведения об использовании системы отдельным пользователем. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 4dcd7c8d14bdaf3c8a9844aab3057d356a53fc91
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857216"
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
   

